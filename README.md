encoded_message = b'\x00\x00\x00\x01\x48\x65\x6c\x6c\x6f\x0a'

def get_message_length (message):
    """
    This method reads the first 4 bytes of the encoded message and saves it as the message length
    :param the encoded message
    :return: the number of lines in the message
    :author: Joe Casper
    """

number_of_lines = get_message_length(encoded_message)

def create_message_array():
    """
    This method creates a two dimensional array that stores the message.
    The number of arrays in the message array equals the number of lines in the encoded message
    :return: a 2d message array
    :author: Joe Casper
    """

messgae = create_message_array()

def read_message(encoded_message):
    """
    Holds a loop that reads the encoded message line by line. This method redirects to the
    read_lines method, where the essage is decoded
    :param: the 2d messgae array that holds the decoded message
    :return: the completed, decoded message stored in an array
    :author: Joe Casper
    """

def read_line(encoded_message):
    """
    Reads a line, byte by byte, until a newline character is found. Each byte is decoded as
    the line is iterated through.
    :param: the message being decoded
    :author: Joe Casper
    """

def save_to_file(message):
    """
    Saves the newly decoded message in a file
    :param the decoded message
    :author: Joe Casper
    """
