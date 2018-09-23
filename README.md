
def next_byte_socket_factory():
    """
    Enter the byte in hexadecimal shorthand
    e.g.
      input a byte: e3

    :return: the byte as a bytes object holding one byte
    :author: Dr. Yoder
    """

    msg = (b'\x00\x00\x00\x04\x4c\x61\x62\x20'
           b'\x31\x0a\x50\x68\x69\x6c\x65\x61'
           b'\x73\x20\x46\x6f\x67\x67\x0a\x0a'
           b'\x54\x68\x69\x73\x20\x69\x73\x20'
           b'\x6d\x79\x20\x6c\x61\x62\x20\x31'
           b'\x20\x61\x73\x73\x69\x67\x6e\x6d'
           b'\x65\x6e\x74\x2e\x0a')

    for b in msg:
        yield bytes((b,))  # b holds the contents of the byte as an int.
        # This converts it back to a bytes object
        # of a single byte.


def next_byte(data_socket):
    return next(data_socket)
    ## the line of code is from his webiste but I do not know where it goes yet 
    
encoded_message = b'\x00\x00\x00\x01\x48\x65\x6c\x6c\x6f\x0a'

#trying to write bytes to a file
with open ("text.txt, 'rb') as binary_file:
binary_file_write('') ##not sure what goes in 
num_bytes_written = binary_file()

#Reading file line by line
with open('text.txt, 'rb') as text_files:
for line in text_file:
print(line) 


    """
    This method reads the first 4 bytes of the encoded message and saves it as the message length
    :param the encoded message
    :return: the number of lines in the message
    :author: Joe Casper and Lauren Lee
   """
with open(path_to_file, 'rb') as binary_byte:
    binary_byte.read()[:4]

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
    :author: Joe Casper and Lauren Lee 
    """


def read_line(encoded_message):
    """
    Reads a line, byte by byte, until a newline character is found. Each byte is decoded as
    the line is iterated through.
    :param: the message being decoded
    :author: Joe Casper and Lauren Lee
    """
new_line = open("myFile, 'rb')
try:
byte = new_line.read(1)
while byte != "":
byte = new_line.read(1)

def save_to_file(message):
    """
    Saves the newly decoded message in a file
    :param the decoded message
    :author: Joe Casper and Lauren Lee
    """
 
 ##there are a lot of errors   
    

>> >> >> > master
