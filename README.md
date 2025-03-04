# sistemas
echo "Introduce el nombre del fichero CSV con los usuarios (nombre,DNI,password):"
    read fichero
    while IFS=, read -r nombre dni password
    do
        sudo useradd $nombre
        echo "$nombre:$password" | chpasswd
        echo "Usuario $nombre dado de alta."
    done < $fichero
