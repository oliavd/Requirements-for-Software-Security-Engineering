$ shellcheck myscript
 
Line 22:
domToRemoveList=()
^-- SC2034: domToRemoveList appears unused. Verify it or export it.
 
Line 56:
  echo $* | sed 's/^\.*//' | sed "s/[]\.|$(){}?+*^]/\\\\&/g" | sed "s/\\//\\\\\//g"
                                                                              ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
       ^-- SC2086: Double quote to prevent globbing and word splitting.
       ^-- SC2048: Use "$@" (with quotes) to prevent whitespace problems.
                                      ^-- SC1117: Backslash is literal in "\.". Prefer explicit escaping: "\\.".
 
Line 68:
    domList=("${domList[@]}" ${validDomain})
                             ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 115:
    source "${piholeDir}/setupVars.conf"
    ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 122:
    grep -e "address=\/${domain}\/" "${wildcardlist}" > /dev/null 2>&1 || bool=false
                                ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
                     ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
 
Line 130:
      if [[ "${#IPV6_ADDRESS}" > 0 ]]; then
                               ^-- SC2071: > is for string comparisons. Use -gt instead.
 
Line 163:
      grep -e "address=\/${domain}\/" "${wildcardlist}" > /dev/null 2>&1 || bool=false
                       ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
                                  ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
 
Line 168:
        sed -i "/address=\/${domain}/Id" "${list}"
                         ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
 
Line 190:
  echo -e "Displaying $string:\n"
                              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 206:
    "-f" | "--force"     ) force=true;;
                           ^-- SC2034: force appears unused. Verify it or export it.

$
