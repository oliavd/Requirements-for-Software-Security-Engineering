$ shellcheck myscript
 
Line 24:
lighttpdConfig=/etc/lighttpd/lighttpd.conf
^-- SC2034: lighttpdConfig appears unused. Verify it or export it.
 
Line 90:
  PKG_INSTALL=(${PKG_MANAGER} --yes --no-install-recommends install)
               ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 108:
  INSTALLER_DEPS=(apt-utils dialog debconf dhcpcd5 git ${iproute_pkg} whiptail)
                                                       ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 110:
  PIHOLE_WEB_DEPS=(lighttpd ${phpVer}-common ${phpVer}-cgi)
                                             ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
                            ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 137:
  PKG_INSTALL=(${PKG_MANAGER} install -y)
               ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 237:
  IPv4dev=$(awk '{for (i=1; i<=NF; i++) if ($i~/dev/) print $(i+1)}' <<< "${route}")
  ^-- SC2034: IPv4dev appears unused. Verify it or export it.
 
Line 251:
  whiptail --msgbox --backtitle "Welcome" --title "Pi-hole automated installer" "\n\nThis installer will transform your device into a network-wide ad blocker!" ${r} ${c}
                                                                                   ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                 ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 254:
  whiptail --msgbox --backtitle "Plea" --title "Free and open source" "\n\nThe Pi-hole is free, but powered by your donations:  http://pi-hole.net/donate" ${r} ${c}
                                                                       ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 257:
  whiptail --msgbox --backtitle "Initiating network interface" --title "Static IP Needed" "\n\nThe Pi-hole is a SERVER so it needs a STATIC IP ADDRESS to function properly.
                                                                                             ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 268:
  local existing_free_kilobytes=$(df -Pk | grep -m1 '\/$' | awk '{print $4}')
        ^-- SC2155: Declare and assign separately to avoid masking return values.
 
Line 320:
      chooseInterfaceCmd=(whiptail --separate-output --radiolist "Choose An Interface (press space to select)" ${r} ${c} ${interfaceCount})
                                                                                                               ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
                                                                                                                         ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
                                                                                                                    ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 335:
  ((($value1&254)==252)) && echo "ULA" || true
                         ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
     ^-- SC2004: $/${} is unnecessary on arithmetic variables.
 
Line 336:
  ((($value1&112)==32)) && echo "GUA" || true
     ^-- SC2004: $/${} is unnecessary on arithmetic variables.
                        ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
 
Line 337:
  ((($value1==254) && (($value2&192)==128))) && echo "Link-local" || true
                                             ^-- SC2015: Note that A && B || C is not if-then-else. C may run when A is true.
                        ^-- SC2004: $/${} is unnecessary on arithmetic variables.
     ^-- SC2004: $/${} is unnecessary on arithmetic variables.
 
Line 342:
  IPV6_ADDRESSES=($(ip -6 address | grep 'scope global' | awk '{print $2}'))
                  ^-- SC2207: Prefer mapfile or read -a to split command output (or quote to avoid splitting).
 
Line 372:
  cmd=(whiptail --separate-output --checklist "Select Protocols (press space to select)" ${r} ${c} 2)
                                                                                         ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
                                                                                              ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 512:
    ip=(${ip})
        ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 580:
      piholeDNS=$(whiptail --backtitle "Specify Upstream DNS Provider(s)"  --inputbox "Enter your desired upstream DNS provider(s), seperated by a comma.\n\nFor example '8.8.8.8, 8.8.4.4'" ${r} ${c} "${prePopulate}" 3>&1 1>&2 2>&3) || \
                                                                                                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 591:
        whiptail --msgbox --backtitle "Invalid IP" --title "Invalid IP" "One or both entered IP addresses were invalid. Please try again.\n\n    DNS Server 1:   $PIHOLE_DNS_1\n    DNS Server 2:   ${PIHOLE_DNS_2}" ${r} ${c}
                                                                                                                                                                              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 600:
        if (whiptail --backtitle "Specify Upstream DNS Provider(s)" --title "Upstream DNS Provider(s)" --yesno "Are these settings correct?\n    DNS Server 1:   $PIHOLE_DNS_1\n    DNS Server 2:   ${PIHOLE_DNS_2}" ${r} ${c}); then
                                                                                                                                                                              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 617:
  LogToggleCommand=(whiptail --separate-output --radiolist "Do you want to log queries?\n (Disabling will render graphs on the Admin page useless):" ${r} ${c} 6)
                                                                                                                                                          ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
                                                                                       ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                     ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 638:
  WebToggleCommand=(whiptail --separate-output --radiolist "Do you wish to install the web admin interface?" ${r} ${c} 6)
                                                                                                             ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
                                                                                                                  ^-- SC2206: Quote to prevent word splitting, or split robustly with mapfile or read -a.
 
Line 820:
    echo -en "\n!!! ERROR - Unable to update package cache. Please try \"${UPDATE_PKG_CACHE}\""
              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 942:
      printf "\n:::\tNo default index.lighttpd.html file found... not backing up"
                   ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1003:
    whiptail --title "Firewall in use" --yesno "We have detected a running firewall\n\nPi-hole currently requires HTTP and DNS port access.\n\n\n\nInstall Pi-hole default firewall rules?" ${r} ${c} || \
                                                                                                                                                 ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                             ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                   ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1004:
    { echo -e ":::\n::: Not installing firewall rulesets."; return 0; }
                  ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1005:
    echo -e ":::\n:::\n Configuring FirewallD for httpd and dnsmasq."
                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1014:
      whiptail --title "Firewall in use" --yesno "We have detected a running firewall\n\nPi-hole currently requires HTTP and DNS port access.\n\n\n\nInstall Pi-hole default firewall rules?" ${r} ${c} || \
                                                                                                                                                 ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                   ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                             ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                       ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                     ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1015:
      { echo -e ":::\n::: Not installing firewall rulesets."; return 0; }
                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1016:
      echo -e ":::\n::: Installing new IPTables firewall rulesets."
                  ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1025:
    echo -e ":::\n::: No active firewall detected.. skipping firewall configuration."
                ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1028:
  echo -e ":::\n::: Skipping firewall configuration."
              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1035:
    if [ ${IPV4_ADDRESS} ]; then
         ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 1058:
  source "${setupVars}"
  ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 1059:
  source "${PI_HOLE_LOCAL_REPO}/advanced/Scripts/webpage.sh"
  ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 1102:
      printf "\n:::\tWarning: 'lighty-enable-mod' utility not found. Please ensure fastcgi is enabled if you experience issues.\n"
                                                                                                                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
              ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                   ^-- SC1117: Backslash is literal in "\t". Prefer explicit escaping: "\\t".
 
Line 1159:
      whiptail --title "SELinux Enforcing Detected" --yesno "SELinux is being Enforced on your system!\n\nPi-hole currently does not support SELinux, but you may still continue with the installation.\n\nNote: Admin UI Will not function fully without setting your policies correctly\n\nContinue installing Pi-hole?" ${r} ${c} || \
                                                                                                      ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                        ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                                                                                                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                                                                         ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                                                                       ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                                                                                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1211:
  UpdateCmd=$(whiptail --title "Existing Install Detected!" --menu "\n\nWe have detected an existing install.\n\nPlease choose from the following options: \n($strAdd)" ${r} ${c} 2 \
                                                                                                               ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                             ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                      ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                    ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
                                                                                                                                                           ^-- SC1117: Backslash is literal in "\n". Prefer explicit escaping: "\\n".
 
Line 1279:
      install -T -m 0755 /tmp/${binary} /usr/bin/pihole-FTL
                              ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 1280:
      rm /tmp/${binary} /tmp/${binary}.sha1
                             ^-- SC2086: Double quote to prevent globbing and word splitting.
              ^-- SC2086: Double quote to prevent globbing and word splitting.
 
Line 1308:
    local rev=$(uname -m | sed "s/[^0-9]//g;")
          ^-- SC2155: Declare and assign separately to avoid masking return values.
 
Line 1309:
    local lib=$(ldd /bin/ls | grep -E '^\s*/lib' | awk '{ print $1 }')
          ^-- SC2155: Declare and assign separately to avoid masking return values.
 
Line 1453:
    source ${setupVars}
    ^-- SC1090: Can't follow non-constant source. Use a directive to specify location.
 
Line 1459:
      DEPS=("${PIHOLE_DEPS[@]}")
      ^-- SC2034: DEPS appears unused. Verify it or export it.
 
Line 1474:
        . /opt/pihole/webpage.sh
        ^-- SC1091: Not following: /opt/pihole/webpage.sh was not specified as input (see shellcheck -x).
 
Line 1475:
        echo "WEBPASSWORD=$(HashPassword ${pw})" >> ${setupVars}
                                         ^-- SC2086: Double quote to prevent globbing and word splitting.

$ 
