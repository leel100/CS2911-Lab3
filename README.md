
def next_byte_socket_factory(encoded_msg):
    """
    Enter the byte in hexadecimal shorthand
    e.g.
      input a byte: e3

    :return: the byte as a bytes object holding one byte
    :author: Dr. Yoder
    """

    for b in encoded_msg:
        yield bytes((b,))  # b holds the contents of the byte as an int.
        # This converts it back to a bytes object
        # of a single byte.


def next_byte(data_socket):
    return next(data_socket)


def get_message_length():
    """
    This method reads the first 4 bytes of the encoded message and saves it as the message length
    :param the encoded message
    :return: the number of lines in the message
    :author: Joe Casper
    """
    length = b''

    # reads the first 4 bytes of the message and appends it to a bytes object
    for counter in range(0,4):
        length += next_byte(data_socket)

    # converts the bytes object to an int, returns the result
    return int.from_bytes(length,"big")


def create_message_array(size):
    """
    This method creates a two dimensional array that stores the message.
    The number of arrays in the message array equals the number of lines in the encoded message
    :return: a 2d message array
    :author: Joe Casper
    """

    array = []

    # for each line long the message is, add one index of arrays to array
    for x in range (0, size):
        array.append([])

    return array


def read_message(size, array):
    """
    Holds a loop that reads the encoded message line by line. This method redirects to the
    read_lines method, where the message is decoded
    :return: the completed, decoded message stored in an array
    :author: Joe Casper
    """
    # Run this line of code for every '/n' in the encoded message
    for counter in range(0, size):
        read_line(array, counter)

    return array


def read_line(array, index):
    """
    Reads a line, byte by byte, until a newline character is found. Each byte is decoded as
    the line is iterated through.
    :author: Joe Casper
    """
    # continue_parsing is marked as false when next_byte returns a newline character
    continue_parsing = True
    while continue_parsing:
        byte = b''
        # append the next byte in the message to a blank bytes object
        byte += next_byte(data_socket)

        # At the current index, decode the bytes object and append it
        array[index].append(byte.decode("ASCII"))

        # if next_byte returned a newline character, break the loop and return to read_message
        if byte == b'\x0a':
            continue_parsing = False


# TODO
def save_to_file(decoded_msg):
    """
    Saves the newly decoded message in a file
    :param decoded_msg the decoded message
    :author: Joe Casper
    """

# TODO read from file instead of hard code
encoded_msg = (b'\x00\x00\x00\x04\x4c\x61\x62\x20'
           b'\x31\x0a\x50\x68\x69\x6c\x65\x61'
           b'\x73\x20\x46\x6f\x67\x67\x0a\x0a'
           b'\x54\x68\x69\x73\x20\x69\x73\x20'
           b'\x6d\x79\x20\x6c\x61\x62\x20\x31'
           b'\x20\x61\x73\x73\x69\x67\x6e\x6d'
           b'\x65\x6e\x74\x2e\x0a')

# Create the generator
data_socket = next_byte_socket_factory(encoded_msg)

# get the message length
msg_length = get_message_length()

# create the blank array
blank_array = create_message_array(msg_length)

# read through the encoded message, store the decoded values in an array
decoded_msg = read_message(msg_length, blank_array)
