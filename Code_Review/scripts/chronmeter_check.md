$ shellcheck myscript
 
Line 48:
    scr_size=( $(stty size 2>/dev/null || echo 24 80) )
               ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 96:
    printf "%s%02d:%02d:%02d\n" "$days" "$hrs" "$mins" "$secs"
                            ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 102:
    source ${coltable}
    ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 133:
    source "/etc/os-release"
    ^-- SC1091: Not following: /etc/os-release was not specified as input (see shellcheck -x).
 
Line 171:
    [[ -n "$setupVars" ]] && source "$setupVars"
                             ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 174:
    ph_ver_raw=($(pihole -v -c 2> /dev/null | sed -n 's/^.* v/v/p'))
                ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 188:
    disk_raw=($(df -B1 / 2> /dev/null | awk 'END{ print $3,$2,$5 }'))
              ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 222:
  cpu_raw=$(ps -eo pcpu,rss --no-headers | grep -E -v "    0")
            ^-- SC2009: Consider using pgrep instead of grepping ps output.
 
Line 243:
      cpu_temp=$(printf "%'.0fc\n" "$(calcFunc "$(< $temp_file) / 1000")")
                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 257:
      cpu_temp=$(printf "%'.0ff\n" "$(calcFunc "($(< $temp_file) / 1000) * 9 / 5 + 32")")
                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 270:
      cpu_temp_str=$(printf ", %'.0fk\n" "$(calcFunc "($(< $temp_file) / 1000) + 273.15")")
                                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 276:
  ram_raw=($(awk '/MemTotal:/{total=$2} /MemFree:/{free=$2} /Buffers:/{buffers=$2} /^Cached:/{cached=$2} END {printf "%.0f %.0f %.0f", (total-free-buffers-cached)*100/total, (total-free-buffers-cached)*1024, total*1024}' /proc/meminfo))
           ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 295:
  stats_raw=($(pihole-FTL "stats"))
             ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 308:
    domains_being_blocked=$(printf "%'.0f\n" "${domains_being_blocked_raw}")
                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 309:
    dns_queries_today=$(printf "%'.0f\n" "${dns_queries_today_raw}")
                                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 310:
    ads_blocked_today=$(printf "%'.0f\n" "${ads_blocked_today_raw}")
                                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 311:
    ads_percentage_today=$(printf "%'.0f\n" "${ads_percentage_today_raw}")
                                        ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 314:
    top_ad_raw=($(pihole-FTL "top-ads (1)"))
                ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 315:
    top_domain_raw=($(pihole-FTL "top-domains (1)"))
                    ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 316:
    top_client_raw=($(pihole-FTL "top-clients (1)"))
                    ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 343:
[0;1;33;93m| ¯[0;1;32;92m_[0;1;36;96m/¯[0;1;34;94m|_[0;1;35;95m_[0;1;31;91m| [0;1;33;93m' [0;1;32;92m\/ [0;1;36;96m_ [0;1;34;94m\ [0;1;35;95m/ [0;1;31;91m-[0;1;33;93m_)[0m$ph_lte_str
                                                                                                                                          ^-- SC1117: Backslash is literal in "\ ". Prefer explicit escaping: "\\ ".
                                                                                                             ^-- SC1117: Backslash is literal in "\/". Prefer explicit escaping: "\\/".
 
Line 344:
[0;1;32;92m|_[0;1;36;96m| [0;1;34;94m|_[0;1;35;95m|  [0;1;33;93m|_[0;1;32;92m||[0;1;36;96m_\[0;1;34;94m__[0;1;35;95m_/[0;1;31;91m_\[0;1;33;93m__[0;1;32;92m_|[0m$ph_ftl_str
                                                                                                                                            ^-- SC1117: Backslash is literal in "\". Prefer explicit escaping: "\\".
                                                                                                  ^-- SC1117: Backslash is literal in "\". Prefer explicit escaping: "\\".
 
Line 348:
    [ -n "$sys_type" ] && printf "%s(%s)%s\n"  "$COL_DARK_GRAY" "$sys_type" "$COL_NC" || printf "\n"
                                                                                                 ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                          ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 350:
    printf "%s\n" "    Uptime: $sys_uptime"
              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 353:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Active: $cpu_taskact of $cpu_tasks tasks" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 356:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "$sys_cores $sys_cores_plu$cpu_freq_str$cpu_temp_str" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 359:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Used: $(hrBytes "$ram_used") of $(hrBytes "$ram_total")" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 362:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Used: $(hrBytes "$disk_used") of $(hrBytes "$disk_total")" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 365:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Gateway: $net_gateway" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 369:
      printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Leased: $ph_dhcp_num of $ph_dhcp_max" "$COL_NC"
                      ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 373:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Blocking: $domains_being_blocked sites" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 376:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "$ads_blocked_today of $dns_queries_today queries" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 379:
    printf "%s(%s)%s\n" "$COL_DARK_GRAY" "Alt DNS: $ph_alts" "$COL_NC"
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".

$ 
