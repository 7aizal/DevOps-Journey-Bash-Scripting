# DevOps-Journey-Bash-Scripting
Bash Scripting – DevOps Learning Journal
Bash scripting has been one of the most valuable tools in my DevOps learning journey so far. It's like giving instructions to your computer in its own language—creating scripts that can automate tasks, respond to different conditions, and process data without constant manual input. Bash scripting not only makes repeated tasks faster but also allows for a lot of creativity and customization.

One of the key advantages of scripting is automation. By combining different commands into a single file, I can create tools that handle complex processes, reduce human error, and increase efficiency. Bash gives you the flexibility to tailor the behavior of scripts using parameters, so a single script can handle multiple scenarios.

For example:

bash

./script.sh parameter1 parameter2
You can use arithmetic in your scripts too:

bash

area=$((length * width))
Readability & Collaboration
I learned that comments (#) are more than just notes—they’re essential. Comments improve readability, help future readers (or yourself) understand the purpose of the script, and make debugging easier by highlighting what the script is supposed to do.

PATH Variable and Script Execution
To run a script from anywhere, I use the $PATH environment variable:

bash

echo $PATH
This shows all directories the shell checks for executable files. Placing a script in one of these directories lets you call it globally.

To add a path:

bash

export PATH=$PATH:/your/custom/path
Conditional Logic – If, Else, Elif
Bash scripts can make decisions using if statements, allowing them to respond to different inputs or situations.

bash

if [ condition ]; then
  # Code block if true
elif [ another_condition ]; then
  # Another code block
else
  # Code block if all else fails
fi
You can use comparison operators like:

-eq: equal

-ne: not equal

-lt: less than

-gt: greater than

-le: less than or equal

-ge: greater than or equal

Combine conditions with:

&& (and)

|| (or)

Nested if statements allow even more complex decision trees.

Loops – While & For
Loops are a powerful way to automate repetition.

While Loop:

bash

count=1
while [ $count -le 3 ]; do
  echo "Count: $count"
  ((count++))
done
While Loop with Array:

bash

fruits=("apple" "banana" "orange")
index=0
while [ $index -lt ${#fruits[@]} ]; do
  echo "Fruit: ${fruits[$index]}"
  ((index++))
done
For Loop:

bash

for (( i=1; i<=5; i++ )); do
  echo "Number: $i"
done
These tools let me iterate through data, files, or tasks in a clean and controlled way.

Error Handling & Exit Codes
Handling errors is crucial in scripting. A script might be managing backups, deployments, or critical data—failure without warning is dangerous.

Useful tools:

echo $?: Shows the exit code of the last command

0 = success

1 = error

set -e: Exit if any command fails

set -u: Exit if using an undefined variable

set -x: Print commands as they’re executed (debugging)

set -eux: Enables all three at once

set -o pipefail: Ensure the pipeline fails if any step fails

Example error-handling logic:

bash

if [ ! -f "$filename" ]; then
  echo "File not found!"
  exit 1
fi
Reading Files in a Script
Option 1:

bash

read_file() {
  local file_path="$1"
  while IFS= read -r line; do
    echo "$line"
  done < "$file_path"
}
Option 2:

bash

process_file() {
  local file_path="$1"
  cat "$file_path" | while IFS= read -r line; do
    echo "$line"
  done
}
Checksums & File Integrity
I also learned about file checksums, which are unique cryptographic hashes that help verify a file’s integrity. They're crucial when ensuring that a file hasn’t been tampered with or corrupted.

Final Thoughts
Bash scripting has opened my eyes to how powerful simple tools can be. It's not just about writing commands—it's about building intelligent, reusable, and flexible systems. This module has laid a strong foundation for future automation work in my DevOps path.

