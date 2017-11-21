$ shellcheck myscript
 
Line 42:
        . /etc/pihole/setupVars.conf
        ^-- SC1091: Not following: /etc/pihole/setupVars.conf was not specified as input (see shellcheck -x).
 
Line 100:
      sources+=(${line})
                ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 111:
        if [ $success = true ]; then
             ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 151:
        err=$(curl -s -L ${cmd_ext} ${heisenbergCompensator} -w %{http_code} -A "${agent}" ${url} -o ${patternBuffer})
                                                                                           ^-- SC2086: Double quote to prevent globbing and word splitting.
                                                                                                     ^-- SC2086: Double quote to prevent globbing and word splitting.
                                                                           ^-- SC1083: This } is literal. Check expression (missing ;/\n?) or quote it.
                                                                 ^-- SC1083: This { is literal. Check expression (missing ;/\n?) or quote it.
                         ^-- SC2086: Double quote to prevent globbing and word splitting.
                                    ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 228:
                        cat "${i}" | tr -d '\r' >> ${piholeDir}/${matterAndLight}
                            ^-- SC2002: Useless cat. Consider 'cmd < file | ..' or 'cmd file | ..' instead.
 
Line 251:
                let numWildcards/=2
                ^-- SC2219: Instead of 'let expr', prefer (( expr )) .
 
Line 265:
        plural=; [[ "${sources[@]}" != "1" ]] && plural=s
                    ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).
 
Line 271:
                urls=("${urls[@]}" ${tmp})
                                   ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 329:
        echo -e "${hostname}\npi.hole" > "${localList}.tmp"
                            ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 361:
                if [[ " ${activeDomains[@]} " =~ ${file} ]]; then
                      ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).
 
Line 380:
        cat ${piholeDir}/${matterAndLight} | \
            ^-- SC2002: Useless cat. Consider 'cmd < file | ..' or 'cmd file | ..' instead.

$ 
