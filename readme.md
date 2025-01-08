#!/bin/bash

# Define the file name
FILE="local.properties"

# Define the property to add
PROPERTY="devMode=true"

# Check if the file exists
if [[ -f "$FILE" ]]; then
  # Check if the property already exists in the file
  if grep -q "^devMode=" "$FILE"; then
    echo "The property 'devMode' already exists in $FILE."
  else
    # Add the property to the file
    echo "$PROPERTY" >> "$FILE"
    echo "The property 'devMode=true' has been added to $FILE."
  fi
else
  echo "File $FILE does not exist. Creating it now."
  echo "$PROPERTY" > "$FILE"
  echo "The property 'devMode=true' has been added to the newly created $FILE."
fi
