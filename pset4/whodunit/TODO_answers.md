0. ## How many different colors does each format support?
        BMP: 24 bits per pixel are common for BMP files, which supports 2^24 =
        16,777,216 colors. 64 bits per pixel is also possible.
        GIF: Store 8 bits at most, so 256 colors.
        JPEG: JPEG images store 24 bits per pixel, so >16 million colors.
        PNG: PNG can store colors with up to 48 bits per pixel, so 2^48 colors.

1. ## Which of the formats supports animation?
        GIF supports animation.
2. ## What’s the difference between lossy and lossless compression?
        Lossless compression = every single bit of data that was originally in
        the file remains after the file is uncompressed.
        Lossy compression = the file is reduced by permanently eliminating
        certain information, especially redundant information.
3.  ## Which of these formats is lossy-compressed?
        JPEG is lossy compressed.
4.  ## What happens, technically speaking, when a file is deleted on a FAT file
    system?
        When the operating system erases a FAT file, 1) the system modifies the
        filename's first character in the file's directory entry to signal that
        the file has been deleted and that the directory entry can be recycled
        and 2) the system moves all of the file's FAT clusters to the hard
        drive's list of free clusters (the actual file data is never touched).
5.  What can someone like you do to ensure (with high probability) that files
    you delete cannot be recovered?
        To ensure deleted files cannot be recovered, the options are:
                1)  destroy the drive,
                2)  degauss the drive (play with the magnetism and likely render
                    the drive useless),
                3)  overwrite the files in a specific way
6.  What’s stdint.h?
        stdint.h is a header file in the C standard library that allows
        programmers to write more portable code by providing a set of typedefs
        that specify exact-width integer types, along with the defined min and
        max values for each type, using macros.
7.  What’s the point of using uint8_t, uint32_t, int32_t, and uint16_t in a
    program?
        These are unsigned and signed integer types from stdint.h. Using well-
        defined types makes the code far easier and safer to port since you
        won't get any surprises when one machine interprets int as 16-bit and
        another as 32-bit. What you type is what you get when you use them.
8.  How many bytes is a BYTE, a DWORD, a LONG, and a WORD, respectively?
        1 byte in a BYTE
        4 bytes in a DWORD (32 bits)
        4 bytes in a LONG (32 bits)
        2 bytes in a WORD (16 bits)
9.  What (in ASCII, decimal, or hexadecimal) must the first two bytes of any BMP
    file be? (Leading bytes used to identify file formats (with high probability)
    are generally called "magic numbers.)"
        The first two bytes of any BMP file must contain ASCII B then ASCII M.
10. What’s the difference between bfSize and biSize?
        bfSize is the size of the bmp file. biSize is the size of the structure.
        Both in bytes.
11. What does it mean if biHeight is negative?
        If biHeight is postive, the image is bottom up. If biHeight is negative,
        the image is bottom down.
12. What field in BITMAPINFOHEADER specifies the BMP’s color depth (i.e., bits
    per pixel)?
        biBitCount specifies the BMP's color depth - the number of bits per
        pixel.
13. Why might fopen return NULL in copy.c:37?
        fopen might return a NULL pointer if the file that fopen is trying to
        write to doesn't exist.
14. Why is the third argument to fread always 1 in our code?
        fread's third argument is always 1 because we are iterating over every
        pixel.
15. What value does copy.c:70 assign padding if bi.biWidth is 3?
        If biWidth is 3:
        int padding =  (4 - (bi.biWidth * sizeof(RGBTRIPLE)) % 4) % 4 = 3.
        This step ensures the number of bytes in every row is a multiple of 4.
16. What does fseek do?
        fseek allows us to change the offset of a pointer.
17. What is SEEK_CUR?
        SEEK_CUR is the current position indicator in the file.
18. whodunit?