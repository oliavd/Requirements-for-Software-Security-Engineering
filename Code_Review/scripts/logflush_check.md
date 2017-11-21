$ shellcheck myscript
 
Line 11:
if [[ "$@" != *"quiet"* ]]; then
      ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).
 
Line 14:
if [[ "$@" == *"once"* ]]; then
      ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).
 
Line 43:
if [[ "$@" != *"quiet"* ]]; then
      ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).

$ 
