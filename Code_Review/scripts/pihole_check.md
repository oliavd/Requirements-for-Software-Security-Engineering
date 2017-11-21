$ shellcheck myscript
 
Line 26:
  source /opt/pihole/webpage.sh
  ^-- SC1091: Not following: /opt/pihole/webpage.sh was not specified as input (see shellcheck -x).
 
Line 52:
  if [[ "$@" == *"-a"* ]]; then
        ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).
 
Line 55:
  if [[ "$@" == *"-w"* ]]; then
        ^-- SC2199: Arrays implicitly concatenate in [[ ]]. Use a loop (or explicit * instead of @).
 
Line 88:
    grep -i -E "(^|\s)${domain}($|\s)" "${list}"
                                  ^-- SC1117: Backslash is literal in "\s". Prefer explicit escaping: "\\s".
                   ^-- SC1117: Backslash is literal in "\s". Prefer explicit escaping: "\\s".
 
Line 113:
  for list in ${lists[@]}; do
              ^-- SC2068: Double quote array expansions to avoid re-splitting elements.
 
Line 115:
      result=$(scanList ${domain} ${list} ${method})
                                          ^-- SC2086: Double quote to prevent globbing and word splitting.
                                  ^-- SC2086: Double quote to prevent globbing and word splitting.
                        ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 119:
      if [[ ${count} > 0 ]]; then
                     ^-- SC2071: > is for string comparisons. Use -gt instead.
 
Line 131:
    local wildcards=($(processWildcards "${domain}"))
                     ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 132:
    for domain in ${wildcards[@]}; do
                  ^-- SC2068: Double quote array expansions to avoid re-splitting elements.
 
Line 133:
      result=$(scanList "\/${domain}\/" ${wildcardlist})
                                    ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
                         ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
 
Line 136:
      if [[ ${count} > 0 ]]; then
                     ^-- SC2071: > is for string comparisons. Use -gt instead.
 
Line 201:
    if [[ $# > 1 ]]; then
             ^-- SC2071: > is for string comparisons. Use -gt instead.
 
Line 209:
        tt=$((${tt}*60))
              ^-- SC2004: $/${} is unnecessary on arithmetic variables.
 
Line 273:
  if [[ "$(grep -i "^#addn-hosts=/" /etc/dnsmasq.d/01-pihole.conf)" ]]; then
        ^-- SC2143: Use grep -q instead of comparing output with [ -n .. ].
 
Line 280:
  elif [[ "$(grep -i "^addn-hosts=/" /etc/dnsmasq.d/01-pihole.conf)" ]]; then
          ^-- SC2143: Use grep -q instead of comparing output with [ -n .. ].
 
Line 322:
  source "${PI_HOLE_SCRIPT_DIR}"/piholeCheckout.sh
  ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.

$ 
