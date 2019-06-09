#Mau Ngpain???
#Rebuild Cant Make You The Real Programmer :)
clear
bi='\033[34;1m' 
i='\033[32;1m' 
pur='\033[35;1m' 
cy='\033[36;1m' 
me='\033[31;1m' 
pu='\033[37;1m' 
ku='\033[33;1m' 

echo Selamat datang $nick ":)"
get_url=$(curl -s http://zlucifer.com/api/sms.php)
cek='curl -s '$get_url 
response=`curl -s -o /dev/null -w "%{http_code}" $cek`
if [[ $response = *sleeping* ]]; then
    echo
    echo "Website Offline/Restart untuk sementara"
else
    echo
    echo "Masukan Nomor Target :  "
    echo contoh 0812xxxxxx
    read target
    echo 
    echo "Berapa Spam Yang Mau Di Kirim (Limit 100)?"
    read paket
    echo
    echo Apakah nomor $target "Dan Yang Mau Dikirim "$paket" Sudah Benar?"
    echo y/n?
    read confirm
    echo
    if [ $confirm = "y" ]; then
        echo Melakukan spam SMS ke nomor $target
        i=0
        max=100
        while [ $i -le $max ]; do
        echo -ne "\nPROSES SPAMMING : $i% "
        sleep 0.03
        if [ $i -eq 100 ]; then
            echo -ne " [Berhasil!]\n"
                       
            echo "Sabar Dlu Jangan Di Close Termux Nya"
            target_do=$get_url'/sms.php?nomor='$target'&paket='$paket


            CURL_RESPONSE=`curl -s -o /dev/null -w "%{http_code}" $target_do`
            echo "SELESAI"
            echo "ERROR??? CHAT ANE LAH"
            sleep 2
            echo "WhatsApp :" " 089527737700"
            echo "Telegram :" " https:/t.me/Mas Qi"
            fi
            let i++
            done
    else
        echo "Error "
    fi
fi
