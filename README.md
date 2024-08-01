#!/bin/bash

# Display script usage
usage() {
    echo "Usage: $0 <D> <WL> <U> <FS>"
    echo "   -h, --help     Show this message and exit"
}

# Help option check
if [[ "$1" == "-h" || "$1" == "--help" ]]; then
    usage
    exit 0
fi

# Check arguments
if [ "$#" -ne 4 ]; then
    echo "Error: Incorrect arguments."
    usage
    exit 1
fi

# Assign variables
D="$1"
WL="$2"
U="$3"
FS="$4"

# Execute ffuf
ffuf -H "Host: FUZZ.$D" -H "User-Agent: SCANNER" -c -w "$WL" -u "$U" -fs "$FS"
