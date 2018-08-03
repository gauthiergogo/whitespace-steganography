# Whitespace Steganography

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

Multiple licenses: You do not have to use the GPL: This code is also part of a freely licensed book. Please have a look at infiniteadventures.de for more information.

## Whitespace Steganography

Use HTML's interpretation of multiple spaces to hide base64 code on any HTML page.

Example:

    wget -O - 'https://en.wikipedia.org/wiki/User:ToBeFree/sandbox?action=edit' | grep -E '\[[0-9]+\]' | sed 's/\s\s\s\s/1/g' | sed 's/\s\s\s/0/g' | sed -r 's/\[[0-9]+\]//g' | tr -d -c '10' | fold -w 6 | tr '\n' ' ' > binary.txt

    bash binary-base64-tobefree.sh binary.txt | base64 -d > decoded-output.txt

----

Useful for ENcoding: Kate for Linux has a "block/rectangular selection" tool.
