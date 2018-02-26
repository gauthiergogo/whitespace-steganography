# Whitespace Steganography

Whitespace steganography for Infinite Adventures 2

Use HTML's interpretation of multiple spaces to hide base64 code on any HTML page. Used by protagonist "Free" in the book "Infinite Adventures 2". http://infiniteadventures.de

Book quote / working example:

    wget -O - 'https://en.wikipedia.org/wiki/User:ToBeFree/sandbox?action=edit' | grep -E '\[[0-9]+\]' | sed 's/\s\s\s\s/1/g' | sed 's/\s\s\s/0/g' | sed -r 's/\[[0-9]+\]//g' | tr -d -c '10' | fold -w 6 | tr '\n' ' ' > binary.txt

Add a space to the end of binary.txt. Use a text editor like nano, gedit or Kate. Then continue:
    
    bash binary-base64-tobefree.sh binary.txt | base64 -d > decoded-output.txt

Useful for encoding: Kate for Linux has a "block/rectangular selection" tool.
