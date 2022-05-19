#!/bin/sh
# Name : ScanPro
# Date : May 2022
# Description : ScanPro is a ScanPro Scan scripts for hacker's.
# Set up symbols
# |
clear
# |
dirty_synced="*"
unpushed="△"
dirty_unpushed="▲"
unpulled="▽"
dirty_unpulled="▼"
unpushed_unpulled="⬡"
dirty_unpushed_unpulled="⬢"
# |
nc="\033[00m"
white="\033[1;37m"
grey="\033[0;37m"
purple="\033[0;35m"
red="\033[1;31m"
green="\033[32m"
yellow="\033[33m"
purple="\033[0;35m"
cyan="\033[1;36m"
cafe="\033[1;33m"
fiuscha="\033[0;35m"
blue="\033[34m"
orange="\033[38;5;122m"
# |
RED="$(printf '\033[31m')"
GREEN="$(printf '\033[32m')"
ORANGE="$(printf '\033[33m')"
BLUE="$(printf '\033[34m')"
MAGENTA="$(printf '\033[35m')"
CYAN="$(printf '\033[36m')"
WHITE="$(printf '\033[37m')"
BLACK="$(printf '\033[30m')"
REDBG="$(printf '\033[41m')"
GREENBG="$(printf '\033[42m')"
ORANGEBG="$(printf '\033[43m')"
BLUEBG="$(printf '\033[44m')"
MAGENTABG="$(printf '\033[45m')"
CYANBG="$(printf '\033[46m')"
WHITEBG="$(printf '\033[47m')"
BLACKBG="$(printf '\033[40m')"
RESETBG="$(printf '\e[0m')"
BLINK="$(printf '\033[5;31m')"
# |
Version="v1.0.0.7"
portsr="0"
close=$(echo "${yellow}\n\t\tPress ${cyan}Enter ${yellow}to go Back \n")
hostip=$(echo "      [${green}?${orange}]   Enter IP Target/Host: ${green}")
ipList=$(echo "      [${green}?${orange}]   Your is IP List File: ${green}")
hostport=$(echo "      [${green}?${orange}]   Enter Port Target:  ${green}")
portrange=$(echo "       [${green}?${orange}]   Enter Port Range 1-65535: ${green}")
lastprompt=$(echo "      [${green}?${orange}]  ${orange}  └──╼${orange}")
log_report=$(echo "      [${green}?${orange}]   Enter Location for OutPut Log:  ${green}")

# |
scanPro_Banner(){
  echo " "
  echo ${green}"    █████████                                ███████████                    "
  echo "   ███░░░░░███                              ░░███░░░░░███                   "
  echo "  ░███    ░░░   ██████   ██████   ████████   ░███    ░███ ████████   ██████ "
  echo "  ░░█████████  ███░░███ ░░░░░███ ░░███░░███  ░██████████ ░░███░░███ ███░░███"
  echo "   ░░░░░░░░███░███ ░░░   ███████  ░███ ░███  ░███░░░░░░   ░███ ░░░ ░███ ░███"
  echo "   ███    ░███░███  ███ ███░░███  ░███ ░███  ░███         ░███     ░███ ░███"
  echo "  ░░█████████ ░░██████ ░░████████ ████ █████ █████        █████    ░░██████ "
  echo "   ░░░░░░░░░   ░░░░░░   ░░░░░░░░ ░░░░ ░░░░░ ░░░░░        ░░░░░      ░░░░░░  \n"
}
scanPro_Banner
# |
scanPro_Icon(){
  echo $red ""
  echo "        ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░                             ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░"
  echo "        ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░                             ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░"
  echo "        ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░                             ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░"
  echo "        ▓▓▓▓▓                        ▓▓▓                       ░▓▓▓▓░"
  echo "        ▓▓▓▓▓                        ▓▓▓                       ░▓▓▓▓░"
  echo "        ▓▓▓▓▓                        ▓▓▓                       ░▓▓▓▓░"
  echo "        ▓▓▓▓▓                ▒▓▓▓▓▓  ▓▓▓  ▓▓▓▓▓▒               ░▓▓▓▓░"
  echo "        ▓▓▓▓▓             ▓▓▓▓▓▓▓▓▓  ▓▓▓  ▓▓▓▓▓▓▓▓░            ░▓▓▓▓░"
  echo "                        ▓▓▓▓▓▓▓▓▓           ▓▓▓▓▓▓▓▓▓                "
  echo "                      ▓▓▓▓▓▓▓▓    ▓▓▓▓▓▓▓▓░    ▓▓▓▓▓▓▓▒              "
  echo "                     ▓▓▓▓▓▓    ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓   ▒▓▓▓▓▓▓             "
  echo "                    ▓▓▓▓▓▓   ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓   ▓▓▓▓▓▓            "
  echo "                   ▓▓▓▓▓▓  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  ▓▓▓▓▓░           "
  echo "                   ▓▓▓▓▓  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░  ▓▓▓▓▓           "
  echo "                          ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                  "
  echo "             ▓▓▓▓▓▓▓▓▓▓░  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  ▓▓▓▓▓▓▓▓▓▓░     "
  echo "                          ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                  "
  echo "                   ▓▓▓▓▓  ░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓   ▓▓▓▓▓           "
  echo "                   ▓▓▓▓▓▓  ░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  ▓▓▓▓▓▒           "
  echo "                    ▓▓▓▓▓▓   ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓   ▓▓▓▓▓▓            "
  echo "                     ▓▓▓▓▓▓▒   ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓   ▒▓▓▓▓▓▓             "
  echo "                      ░▓▓▓▓▓▓▒    ░▓▓▓▓▓▓░     ▓▓▓▓▓▓▓▓              "
  echo "                        ▓▓▓▓▓▓▓▓▓▓         ▓▓▓▓▓▓▓▓▓░                "
  echo "        ▓▓▓▓▓             ▒▓▓▓▓▓▓▓▓  ▓▓▓  ▓▓▓▓▓▓▓▓▓            ░▓▓▓▓░"
  echo "        ▓▓▓▓▓                 ▓▓▓▓▓  ▓▓▓  ▓▓▓▓▓                ░▓▓▓▓░"
  echo "        ▓▓▓▓▓                        ▓▓▓                       ░▓▓▓▓░"
  echo "        ▓▓▓▓▓                        ▓▓▓                       ░▓▓▓▓░"
  echo "        ▓▓▓▓▓░                       ▓▓▓                       ░▓▓▓▓░"
  echo "        ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░                             ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░"
  echo "        ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░                             ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░"
  echo "        ░░░░░░░░░░░░░░░                              ░░░░░░░░░░░░░░░ "
  echo ""
}
scanPro_Icon
# |
scanPro_About(){
  echo $green"        =========================================================    "
  echo $cyan"          Script by             $white":" $orange Leon Yaakobov ( #AnLoMinus ) "
  echo $cyan"          Version               $white":" $orange $Version  "
  echo $cyan"          Follow me on Github   $white":" $orange github.com/Anlominus "
  echo $cyan"          Contact me on Telegram $white":" $orange @Anlominus "
  echo $green"        =========================================================    "
}
scanPro_About
# |
PromptFun(){
  echo ""
  echo "${orange}        ┌──[${CYAN}Anlominus${purple}👽${red}Scan${BLUE}Pro$~${orange}]${cyan}"
}
prompt="$(PromptFun)"
ReadSomthing(){
  echo "
$cWall    ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓$cWall
$cWall    ▓  ╔═══════════════════════════════════════╗  ▓$cWall
$cWall    ▓  ╠═>   Press ENTER for back to Menu   <==║  ▓$cWall
$cWall    ▓  ╚═══════════════════════════════════════╝  ▓$cWall
$cWall    ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓$cWall"
  echo -n ""
  read read_somthing
}
# Basic Information
choose_Target(){
  ip_List(){
    echo "      ${red}  |"
    echo "      ${cyan}  |---------------------------------"
    read -p "${ipList} " iplist
    echo "      ${cyan}  |---------------------------------"
    echo "      ${red}  |"
  }
  port_Range(){
    echo "      ${red}  |"
    echo "      ${cyan}  |---------------------------------"
    read -p  " ${portrange}" portrange
    echo "      ${cyan}  |---------------------------------"
    echo "      ${red}  |"
  }
  What_IP(){
    echo "      ${red}  |"
    echo "      ${cyan}  |---------------------------------"
    read -p  " ${hostip}" host
    echo "      ${cyan}  |---------------------------------"
    echo "      ${red}  |"
  }
  What_PORT(){
    echo "      ${red}  |"
    echo "      ${cyan}  |---------------------------------"
    read -p  " ${hostport}" port
    echo "      ${cyan}  |---------------------------------"
    echo "      ${red}  |"
  }
  what_LogPath(){
    echo "      ${red}  |"
    echo "      ${cyan}  |---------------------------------"
    read -p  " ${log_report}" namefile
    echo "      ${cyan}  |---------------------------------"
    echo "      ${red}  |"
  }
  What_IP
  What_PORT
  what_LogPath
  sleep 0.94

}
choose_Target
your_choice(){
  if  [ -n ${namefile} ] ; then
    log_Path="ScanProLog/ScanProX.log"
  fi
  echo "${cyan}          |"
  echo "${cyan}          |${green} [#] ${cyan}Target Information"
  echo "${cyan}          |-----------------------------"
  echo "${cyan}          |${green} [!] ${cafe}IP/Host Target:${orange} ${host}"
  echo "${cyan}          |${green} [!] ${cafe}Port Target:${orange} $port"
  echo "${cyan}          |${green} [!] ${cafe}Log OutPut Location:${orange} $log_Path"
  echo "${cyan}          |-----------------------------------------------"
  echo "${cyan}          |${green} [!] ${cyan}Check if you provide right information"
  echo "${cyan}          |"
  echo $green"        =========================================================    "
}
prcscn(){
  clear
  echo "${yellow}\n[!] Scanning: ${cyan}${IP_TARGET}${yellow} [ Please Wait ]\n"
  echo " "
}
# Menu Contents
Menu(){
  while true; do
    #statements
    clear
    echo " "
    echo " "
    scanPro_Banner
    scanPro_About
    your_choice
    #statements
    echo ""
    echo "          [#] ScanPro Menu ${cyan}"
    echo "              [1] Target Selection"
    echo "              [2] Port Selection"
    echo "              [3] Scan Types"
    echo "              [4] Service and Operating System Detection"
    echo "              [5] Output formats"
    echo "              [6] NSE Scripting"
    echo "              [7] HTTP info gathering"
    echo "              [8] Timing and Performance"
    echo "         "
    echo "              [m] Main Menu"
    echo "              [x] Exit"
    echo " "
    echo "      ${prompt}"
    read -p "        └──╼ Enter selection [0-7] > " cmd
    echo " "
    case ${cmd} in
      1)
      nts
      ReadSomthing
      ;;
      2)
      nps
      ReadSomthing
      ;;
      3)
      npst
      ReadSomthing
      ;;
      4)
      saod
      ReadSomthing
      ;;
      5)
      nof
      ReadSomthing
      ;;
      6)
      ddwns
      ReadSomthing
      ;;
      7)
      hsi
      ReadSomthing
      ;;
      8)
      timing
      ReadSomthing
      ;;
      m)
      Menu
      ;;
      x)
      clear
      break
      ;;
      *)
      echo "Invalid entry."
      sleep 0.3
      ;;
    esac
  done
}
#1 Nmap Target Selection
nts(){
  while true; do
    #statements
    clear
    your_choice
    #statements
    echo ""
    echo "${cafe} [1] Nmap Target Selection ${cyan}"
    echo ""
    echo "     [1] Scan a single IP	nmap 192.168.1.1"
    echo "     [2] Scan a host	nmap www.testhostname.com"
    echo "     [3] Scan a range of IPs	nmap 192.168.1.1-20"
    echo "     [4] Scan a subnet	nmap 192.168.1.0/24"
    echo "     [5] Scan targets from a text file	nmap -iL list-of-ips.txt"
    echo " "
    echo "      [m] Main Menu"
    echo "      [x] Exit"
    echo " "
    echo "      ${prompt}"
    read -p "        └──╼ Enter selection [0-4] > " cmd
    case ${cmd} in
      1)
      #statements
      echo "     [1] Scan a single IP	nmap 192.168.1.1"
      nmap ${host}

      ReadSomthing
      ;;
      2)
      #statements
      echo "     [2] Scan a host	nmap www.testhostname.com"
      nmap ${host}

      ReadSomthing
      ;;
      3)
      echo "     [3] Scan a range of IPs	nmap 192.168.1.1-20"
      nmap ${host}-20

      ReadSomthing
      ;;
      4)
      echo "     [4] Scan a subnet	nmap 192.168.1.0/24"
      nmap ${host}/24

      ReadSomthing
      ;;
      5)
      echo "     [5] Scan targets from a text file	nmap -iL list-of-ips.txt"
      ip_List
      nmap -iL ${iplist}

      ReadSomthing
      ;;
      m)
      Menu
      ;;
      x)
      clear
      exit
      ;;
      *)
      echo "Invalid entry."
      sleep 0.3
      ;;
    esac
  done
}
#2 Nmap Port Selection
nps(){
    while true; do
      #statements
      clear
      your_choice
      #statements
      echo ""
      echo "${cafe} [2] Nmap Port Selection ${cyan}"
      echo "     [1] Scan a single Port	nmap -p 22 192.168.1.1"
      echo "     [2] Scan a range of ports	nmap -p 1-100 192.168.1.1"
      echo "     [3] Scan a range of ports	nmap -p 1-500 192.168.1.1"
      echo "     [4] Scan 100 most common ports (Fast)	nmap -F 192.168.1.1"
      echo "     [5] Scan all 65535 ports	nmap -p- 192.168.1.1"
      echo " "
      echo "      [m] Main Menu"
      echo "      [x] Exit"
      echo " "
      echo "      ${prompt}"
      read -p " └──╼ Enter selection [0-7] > " cmd
      case ${cmd} in
        1)
        #statements
        echo "     [1] Scan a single Port	nmap -p 22 192.168.1.1"
        nmap -p ${portsr} ${host}

        ReadSomthing
        ;;
        2)
        #statements
        echo "     [2] Scan a range of ports	nmap -p 1-100 192.168.1.1"
        nmap -Pn ${host} -p $portsr-100

        ReadSomthing
        ;;
        3)
        #statements
        echo "     [3] Scan a range of ports	nmap -p 1-500 192.168.1.1"
        nmap -p ${portsr}-255 ${host}

        ReadSomthing
        ;;
        4)
        #statements
        echo "     [4] Scan 100 most common ports (Fast)	nmap -F 192.168.1.1"
        nmap -F ${host}

        ReadSomthing
        ;;
        5)
        #statements
        echo "     [5] Scan all 65535 ports	nmap -p- 192.168.1.1"
        nmap -p- ${host}

        ReadSomthing
        ;;
        m)
        Menu
        ;;
        x)
        clear
        exit
        ;;
        *)
        echo "Invalid entry."
        sleep 0.3
        ;;
      esac
    done
echo ""
echo ""
}
#3 Nmap Port Scan types
npst(){
  while true; do
    #statements
    clear
    your_choice
    #statements
    echo ""
    echo "${cafe} [3] Nmap Port Scan types ${cyan}"
    echo "     [1] Scan using TCP connect	nmap -sT 192.168.1.1"
    echo "     [2] Scan using TCP SYN scan (default)	nmap -sS 192.168.1.1"
    echo "     [3] Scan UDP ports	nmap -sU -p 123,161,162 192.168.1.1"
    echo "     [4] Scan selected ports - ignore discovery	nmap -Pn -F 192.168.1.1"
    echo " "
    echo "      [m] Main Menu"
    echo "      [x] Exit"
    echo " "
    echo "      ${prompt}"
    read -p "        └──╼ Enter selection [0-4] > " cmd
    case ${cmd} in
      1)
      #statements
      echo "     [1] Scan using TCP connect	nmap -sT 192.168.1.1"
      nmap -sT ${host}

      ReadSomthing
      ;;
      2)
      #statements
      echo "     [2] Scan using TCP SYN scan (default)	nmap -sS 192.168.1.1"
      nmap -sS ${portrange} ${host}

      ReadSomthing
      ;;
      3)
      echo "     [3] Scan UDP ports	nmap -sU -p 123,161,162 192.168.1.1"
      nmap -sU -p ${host}

      ReadSomthing
      ;;
      4)
      echo "     [4] Scan selected ports - ignore discovery	nmap -Pn -F 192.168.1.1"
      nmap -Pn -F ${host}

      ReadSomthing
      ;;
      m)
      Menu
      ;;
      x)
      clear
      exit
      ;;
      *)
      echo "Invalid entry."
      sleep 0.3
      ;;
    esac
  done
}
#4 Service and OS Detection
saod(){
  while true; do
    #statements
    clear
    your_choice
    #statements
    echo ""
    echo "${cafe} [4] Service and OS Detection ${cyan}"
    echo "     [1] Detect OS and Services	nmap -A 192.168.1.1"
    echo "     [2] Standard service detection	nmap -sV 192.168.1.1"
    echo "     [3] More aggressive Service Detection	nmap -sV --version-intensity 5 192.168.1.1"
    echo "     [4] Lighter banner grabbing detection	nmap -sV --version-intensity 0 192.168.1.1"
    echo "     [5] Detect OS nmap -O 192.168.1.1"
    echo " "
    echo "      [m] Main Menu"
    echo "      [x] Exit"
    echo " "
    echo "      ${prompt}"
    read -p "        └──╼ Enter selection [0-4] > " cmd
    case ${cmd} in
      1)
      #statements
      echo "     [1] Detect OS and Services	nmap -A 192.168.1.1"
      nmap -A ${host}

      ReadSomthing
      ;;
      2)
      #statements
      echo "     [2] Standard service detection	nmap -sV 192.168.1.1"
      nmap -sV ${portrange} ${host}

      ReadSomthing
      ;;
      3)
      echo "     [3] More aggressive Service Detection	nmap -sV --version-intensity 5 192.168.1.1"
      nmap -sV --version 5 ${host}

      ReadSomthing
      ;;
      4)
      echo "     [4] Lighter banner grabbing detection	nmap -sV --version-intensity 0 192.168.1.1"
      nmap -sV --version 1 ${host}

      ReadSomthing
      ;;
      5)
      echo "     [5] Detect OS nmap -O 192.168.1.1"
      nmap -O ${host}

      ReadSomthing
      ;;
      m)
      Menu
      ;;
      x)
      clear
      exit
      ;;
      *)
      echo "Invalid entry."
      sleep 0.3
      ;;
    esac
  done
echo ""
}
#5 Nmap Output Formats
nof(){
echo ""
echo "${cafe} [5] Nmap Output Formats ${cyan}"
echo "     [1] Save default output to file	nmap -oN outputfile.txt 192.168.1.1"
echo "     [2] Save results as XML	nmap -oX outputfile.xml 192.168.1.1"
echo "     [3] Save results in a format for grep	nmap -oG outputfile.txt 192.168.1.1"
echo "     [4] Save in all formats	nmap -oA outputfile 192.168.1.1"
echo ""
}
#6 Digging deeper with NSE Scripts
ddwns(){
  while true; do
    #statements
    clear
    your_choice
    #statements
    echo ""
    echo "${cafe} [6] Digging deeper with NSE Scripts ${cyan}"
    echo "     [1] Scan using default safe scripts	nmap -sV -sC 192.168.1.1"
    echo "     [2] Get help for a script	nmap --script-help=ssl-heartbleed"
    echo "     [3] Scan using a specific NSE script	nmap -sV -p 443 –script=ssl-heartbleed.nse 192.168.1.1"
    echo "     [4] Scan with a set of scripts	nmap -sV --script=smb* 192.168.1.1"
    echo "     [5] Vulnerability Script	nmap -sV --script=vuln 192.168.1.1"
    echo " "
    echo "      [m] Main Menu"
    echo "      [x] Exit"
    echo " "
    echo "      ${prompt}"
    read -p "        └──╼ Enter selection [0-4] > " cmd
    case ${cmd} in
      1)
      #statements
      echo "     [1] Scan using default safe scripts	nmap -sV -sC 192.168.1.1"
      nmap -sV -sC ${host}

      ReadSomthing
      ;;
      2)
      #statements
      echo "     [2] Get help for a script	nmap --script-help=ssl-heartbleed"
      nmap --script-help=ssl-heartbleed

      ReadSomthing
      ;;
      3)
      #statements
      echo "     [3] Scan using a specific NSE script	nmap -sV -p 443 –script=ssl-heartbleed.nse 192.168.1.1"
      nmap -sV -p 443 --script=ssl-heartbleed.nse ${host}

      ReadSomthing
      ;;
      4)
      #statements
      echo "     [4] Scan with a set of scripts	nmap -sV --script=smb* 192.168.1.1"
      nmap -sV --script=smb*  ${host}

      ReadSomthing
      ;;
      5)
      #statements
      echo "     [5] Vulnerability Script	nmap -sV --script=vuln 192.168.1.1"
      nmap -A -sC --script=vuln  ${host}

      ReadSomthing
      ;;
      m)
      Menu
      ;;
      x)
      clear
      exit
      ;;
      *)
      echo "Invalid entry."
      sleep 0.3
      ;;
    esac
  done
echo ""
}
#7 HTTP Service Information
hsi(){
  while true; do
  #statements
  clear
  your_choice
  #statements
  echo ""
  echo "${cafe} [#] HTTP Service Information ${cyan}"
  echo "     [1] Gather page titles from HTTP services	nmap --script=http-title 192.168.1.0/24"
  echo "     [2] Get HTTP headers of web services	nmap --script=http-headers 192.168.1.0/24"
  echo "     [3] Find web apps from known paths	nmap --script=http-enum 192.168.1.0/24"
  echo " "
  echo "      [m] Main Menu"
  echo "      [x] Exit"
  echo " "
  echo "      ${prompt}"
  read -p "        └──╼ Enter selection [0-4] > " cmd
  case ${cmd} in
    1)
    #statements
    echo "     [1] Gather page titles from HTTP services	nmap --script=http-title 192.168.1.0/24"
    nmap --script=http-title ${host}/24

    ReadSomthing
    ;;
    2)
    #statements
    echo "     [2] Get HTTP headers of web services	nmap --script=http-headers 192.168.1.0/24"
    nmap --script=http-header ${host}/24

    ReadSomthing
    ;;
    3)
    #statements
    echo "     [3] Find web apps from known paths	nmap --script=http-enum 192.168.1.0/24"
    nmap --script=http-enum ${host}/24

    ReadSomthing
    ;;
    x)
    clear
    exit
    ;;
    *)
    echo "Invalid entry."
    sleep 0.3
    ;;
  esac
done
echo ""
}
#8 HTTP Service Information
timing(){
  while true; do
    #statements
    clear
    your_choice
    #statements
    echo ""
    echo "${cafe} [8] Timing and Performance ${cyan}"
    echo ""
    echo "     [0] Paranoid (0) Intrusion Detection System evasion"
    echo "     [1] Sneaky (1) Intrusion Detection System evasion"
    echo "     [2] Polite (2) slows down the scan to use less bandwidth and use less target machine resources"
    echo "     [3] Normal (3) which is default speed"
    echo "     [4] Aggressive (4) speeds scans; assumes you are on a reasonably fast and reliable network"
    echo "     [5] Insane (5) speeds scan; assumes you are on an extraordinarily fast network"
    echo " "
    echo "      [m] Main Menu"
    echo "      [x] Exit"
    echo " "
    echo "      ${prompt}"
    read -p "        └──╼ Enter selection [0-4] > " cmd
    case ${cmd} in
      0)
      #statements
      echo "     [0] Paranoid (0) Intrusion Detection System evasion"
      nmap ${iplist} -T0

      ReadSomthing
      ;;
      1)
      #statements
      echo "     [1] Sneaky (1) Intrusion Detection System evasion"
      nmap ${iplist} -T1

      ReadSomthing
      ;;
      2)
      echo "     [2] Polite (2) slows down the scan to use less bandwidth and use less target machine resources"
      nmap ${iplist} -T2

      ReadSomthing
      ;;
      3)
      echo "     [3] Normal (3) which is default speed"
      nmap ${iplist} -T3

      ReadSomthing
      ;;
      4)
      echo "     [4] Aggressive (4) speeds scans; assumes you are on a reasonably fast and reliable network"
      ip_List
      nmap ${iplist} -T4

      ReadSomthing
      ;;
      5)
      echo "     [5] Insane (5) speeds scan; assumes you are on an extraordinarily fast network"
      ip_List
      nmap ${iplist} -T5

      ReadSomthing
      ;;
      m)
      Menu
      ;;
      x)
      clear
      exit
      ;;
      *)
      echo "Invalid entry."
      sleep 0.3
      ;;
    esac
  done
  # Timing and Performance

}


Menu
