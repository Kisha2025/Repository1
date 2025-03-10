!/bin/bash
case $1 in
        "-d")
        domain=$2
        if [[ -z ${domain} ]]
        then
                echo "Error"
                exit 128
        fi
        while read sub
        do
                if host "$sub.$domain" &> /dev/null
                then
                        echo "$sub.$domain"
                fi
        done < wordlist
        ;;
        "-h")
                echo "show -d domain"
                ;;
         *)
        echo "ERRoR"
        exit 127
-- INSERT --                                                 1,1           Top

