$ shellcheck myscript
 
Line 12:
PH_TEST="true" source "${PI_HOLE_FILES_DIR}/automated install/basic-install.sh"
^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 20:
source "${setupVars}"
        ^-- SC2154: setupVars is referenced but not assigned.
^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 24:
red="\e[1;31m"
     ^-- SC1117: Backslash is literal in "\e". Prefer explicit escaping: "\\e".
 
Line 25:
def="\e[0m"
     ^-- SC1117: Backslash is literal in "\e". Prefer explicit escaping: "\\e".
 
Line 58:
  cd "${directory}"
  ^-- SC2164: Use 'cd ... || exit' or 'cd ... || return' in case cd fails.
 
Line 117:
    if ! is_repo "${webInterfaceDir}" ; then
                  ^-- SC2154: webInterfaceDir is referenced but not assigned.
 
Line 156:
    echo -n "::: Fetching remote branches for Pi-hole core from ${piholeGitUrl} ... "
                                                                ^-- SC2154: piholeGitUrl is referenced but not assigned.
 
Line 161:
    corebranches=($(get_available_branches "${PI_HOLE_FILES_DIR}"))
                  ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 174:
    echo -n "::: Fetching remote branches for the web interface from ${webInterfaceGitUrl} ... "
                                                                     ^-- SC2154: webInterfaceGitUrl is referenced but not assigned.
 
Line 179:
    webbranches=($(get_available_branches "${webInterfaceDir}"))
                 ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).

$ 
