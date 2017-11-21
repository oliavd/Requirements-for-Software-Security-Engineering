$ shellcheck myscript
 
Line 29:
WHITELISTMATCHES="/tmp/whitelistmatches.list"
^-- SC2034: WHITELISTMATCHES appears unused. Verify it or export it.
 
Line 47:
source ${VARSFILE}
^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 98:
  user=$(echo ${1} | cut -f 3 -d ' ' | cut -c 2-)
              ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 99:
  process=$(echo ${1} | cut -f 2 -d ' ' | cut -c 2-)
                 ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 101:
  && echo ":::       Correctly configured." \
  ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 199:
  local file_found=$(files_check "${1}") \
        ^-- SC2155: Declare and assign separately to avoid masking return values.
 
Line 200:
   && (source "${1}" &> /dev/null && echo "${file_found} and was successfully sourced") \
   ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
       ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 208:
        local distro="$(cat /etc/*release)" && block_parse "${distro}" || (log_echo "Distribution details not found." && soft_fail=1)
                                                                                                                         ^-- SC2030: Modification of soft_fail is local (to subshell caused by (..) group).
                                            ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
              ^-- SC2155: Declare and assign separately to avoid masking return values.
 
Line 209:
        return "${soft_fail}"
                ^-- SC2031: soft_fail was modified in a subshell. That change might be lost.
 
Line 214:
  log_write $(uname -m) && return 0 || return 1
            ^-- SC2046: Quote this to prevent word splitting.
 
Line 229:
  local gravity=${2}
        ^-- SC2034: gravity appears unused. Verify it or export it.
 
Line 232:
  local ip_addr_list="$(ip -${protocol} addr show dev ${PIHOLE_INTERFACE} | awk -F ' ' '{ for(i=1;i<=NF;i++) if ($i ~ '/^inet/') print $(i+1) }')"
                                                      ^-- SC2086: Double quote to prevent globbing and word splitting.
        ^-- SC2155: Declare and assign separately to avoid masking return values.
                            ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 239:
    ip_ping_check ${protocol}
                  ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 240:
    return $(( 0 + $? ))
                   ^-- SC2181: Check exit code directly with e.g. 'if mycmd;', not indirectly with $?.
 
Line 259:
  local ip_def_gateway=$(ip -${protocol} route | grep default | cut -d ' ' -f 3)
        ^-- SC2155: Declare and assign separately to avoid masking return values.
                             ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 262:
    if ! ping_gateway="$(${cmd} -q -W 3 -c 3 -n ${ip_def_gateway} -I ${PIHOLE_INTERFACE} | tail -n 3)"; then
                                                                     ^-- SC2086: Double quote to prevent globbing and word splitting.
                                                ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 270:
    if ! ping_inet="$(${cmd} -q -W 3 -c 3 -n ${g_addr} -I ${PIHOLE_INTERFACE} | tail -n 3)"; then
                                                          ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 286:
  lsof_value=$(lsof -i ${1}:${2} -FcL | tr '\n' ' ') \
                            ^-- SC2086: Double quote to prevent globbing and word splitting.
                       ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 287:
  && lsof_parse "${lsof_value}" "${3}" \
  ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 300:
        lsof_value=$(lsof -i 4:${2} -FcL | tr '\n' ' ') \
                               ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 363:
        log_write $(dig +short chaos txt cachesize.bind)
                  ^-- SC2046: Quote this to prevent word splitting.
 
Line 365:
        log_write $(dig +short chaos txt servers.bind)
                  ^-- SC2046: Quote this to prevent word splitting.
 
Line 376:
                log_write $(systemctl is-active "${i}")
                          ^-- SC2046: Quote this to prevent word splitting.
 
Line 391:
  printf "::: Logging will automatically teminate in %s seconds\n" "${TIMEOUT}"
                                                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 394:
    printf ":::\t%s seconds left. " "${tuvix}"
               ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
 
Line 396:
      printf "\r"
              ^-- SC1117: Backslash is literal in "\r". Prefer explicit escaping: "\\r".
 
Line 398:
      printf "\n"
              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 410:
        echo -e "::: Try loading a site that you are having trouble with now from a client web browser.. \n:::\t(Press CTRL+C to finish logging.)"
                                                                                                              ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
                                                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 418:
                printf ":::\tNo pihole.log file found!\n"
                           ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
                                                      ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 439:
          tricorder=$(cat /var/log/pihole_debug.log | nc tricorder.pi-hole.net 9999)
                          ^-- SC2002: Useless cat. Consider 'cmd < file | ..' or 'cmd file | ..' instead.
 
Line 444:
                          tricorder=$(cat /var/log/pihole_debug.log | nc tricorder.pi-hole.net 9999)
                                          ^-- SC2002: Useless cat. Consider 'cmd < file | ..' or 'cmd file | ..' instead.
 
Line 485:
ip_check 6 ${IPV6_ADDRESS}
           ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 486:
ip_check 4 ${IPV4_ADDRESS}
           ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 514:
        && log_write "${GRAVITYFILE} is ${gravity_length} lines long." \
        ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 520:
  && log_write "${PIHOLELOG} is ${pihole_length} lines long." \
  ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 524:
  && log_write "${PIHOLELOG} is ${pihole_size}." \
  ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 530:
  && log_write "${FTLLOG} is ${FTL_length} lines long." \
  ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 534:
  && log_write "${FTLLOG} is ${FTL_size}." \
  ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.

$ 
