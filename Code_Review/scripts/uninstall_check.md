$ shellcheck myscript
 
Line 39:
                rpm -qa | grep ^$1- > /dev/null
                                ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 65:
        while [ "$(ps a | awk '{print $1}' | grep "${pid}")" ]; do
                ^-- SC2143: Use grep -q instead of comparing output with [ -n .. ].
 
Line 70:
                printf "\b\b\b\b\b\b"
                                  ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                                ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                        ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                          ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                            ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                              ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
 
Line 72:
        printf "    \b\b\b\b"
                          ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                        ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                      ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
                    ^-- SC1117: Backslash is literal in "\b". Prefer explicit escaping: "\\b".
 
Line 79:
                package_check ${i} > /dev/null
                              ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 80:
                if [ $? -eq 0 ]; then
                     ^-- SC2181: Check exit code directly with e.g. 'if mycmd;', not indirectly with $?.
 
Line 84:
                                        [Yy]* ) printf ":::\tRemoving %s..." "${i}"; ${SUDO} ${PKG_REMOVE} "${i}" &> /dev/null & spinner $!; printf "done!\n"; break;;
                                                                                             ^-- SC2086: Double quote to prevent globbing and word splitting.
                                                           ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
                                                                                                                                                          ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 85:
                                        [Nn]* ) printf ":::\tSkipping %s\n" "${i}"; break;;
                                                                        ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                           ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
 
Line 86:
                                        * ) printf "::: You must answer yes or no!\n";;
                                                                                  ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 90:
                        printf ":::\tPackage %s not installed... Not removing.\n" "${i}"
                                   ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
                                                                              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 100:
        package_cleanup &> /dev/null & spinner $!; printf "done!\n";
                                                                ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 165:
        printf "::: Finished removing PiHole from your system. Sorry to see you go!\n"
                                                                                   ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 166:
        printf "::: Reach out to us at https://github.com/pi-hole/pi-hole/issues if you need help\n"
                                                                                                 ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 167:
        printf "::: Reinstall by simpling running\n:::\n:::\tcurl -sSL https://install.pi-hole.net | bash\n:::\n::: at any time!\n:::\n"
                                                 ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                           ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
                                                                                                                                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                      ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 168:
        printf "::: PLEASE RESET YOUR DNS ON YOUR ROUTER/CLIENTS TO RESTORE INTERNET CONNECTIVITY!\n"
                                                                                                  ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".

$ 
