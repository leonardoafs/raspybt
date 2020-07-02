# raspybt
Sistema de Comunicação entre Raspberry Pi 3B e celular Android via Bluetooth e usando Python3

## 0. Documentação RasPyBT

Este README visa auxiliar na instalação de um sistema de comunicação entre a Raspberry Pi 3B e um celular Android via Bluetooth e usando Python3.
Primeiramente vamos configurar o Raspberry. Depois, vamos configurar a comunicação.


### Pré-Requisitos
 * **Raspberry Pi 3B ou 3B+**.
 * **Celular Android**.
 * **Teclado e Mouse, ou acesso à mesma rede para acesso via SSH**.
 
## 1. Instalação Android

Na PlayStore, baixe e instale o aplicativo `Serial Bluetooth Terminal`. Ative o Bluetooth do aparelho.

## 2. Instalação Raspberry

Abra o arquivo de configuração usando o comando `sudo vim /etc/systemd/system/dbus-org.bluez.service`.
Modifique a linha que começa com `ExecStart` para `ExecStart=/usr/lib/bluetooth/bluetoothd -C`.
Neste mesmo arquivo, logo após `ExecStart`, inclua a linha `ExecStartPost=/usr/bin/sdptool add SP`.
Com isso, salve com o comando `:x`  e reinicie com `sudo reboot`.

## 3. Conexão

Agora, procure o bluetooth `rasperrypi` no seu celular. Após conectar, digite no terminal `sudo rfcomm watch hci0`.
Com isso, abra o app Serial Bluetooth Terminal. Clique em `Devices` e selecione `raspberrypi`.

