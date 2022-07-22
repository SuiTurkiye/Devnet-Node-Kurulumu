# Sui Node Kurulumu

İlk önce sudoyu kuralım
```
sudo apt install
```
Sonrasında screen'i yükleyelim

```
apt install screen
```

Şimdi de bir screen oluşturalım

```
screen -S sui
```

Artık full node'umuzu yükleyebiliriz

```
wget -O sui.sh https://raw.githubusercontent.com/kj89/testnet_manuals/main/sui/sui.sh && chmod +x sui.sh && ./sui.sh
```

Bu işlem biraz zaman alabilir

Ardından node'umuzun durumunu kontrol etmek için aşağıdaki komutu çalıştırabiliriz

```
service suid status
```

Aşağıdaki hatayı almanız durumunda;

```
Unit suid.service could not be found.
```

Şu komutları sırasıyla çalıştırabilirsiniz:

```
sudo ufw enable
sudo ufw allow 9000
sudo ufw allow 9184
sudo ufw allow 8080
cd sui 
sed -i 's/127.0.0.1/0.0.0.0/' fullnode-template.yaml
docker-compose restart
```
