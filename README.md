
# Procedimento do F450 com OmnibusF4v3
- ### OS: Ubuntu

### 1. Instalar a firmware ArduCopter na controladora:
- Conectar via USB a controladora ao computador.
	> Garanta que o cabo usb está bom realmente, no Linux basta usar o comando 'lsusb' e verificar se o dispositivo está listado.
- Colcar a placa em modo DFU.
	> Desconecte a placa depois conecte o cabo usb novamente com o botão de bootloader pressionado.
- Verificar se a controladora está em modo DFU com os comandos:
	> sudo apt install dfu-util

	> dfu-util --list

- Instalar firmware na controladora via programa CleanFlight (<a link="https://chrome.google.com/webstore/detail/cleanflight-configurator/enacoimjcgeinfnnnpajinjgmkahmfgb">Install CleanFlight Chrome extension</a>):
	> Abrir o CleanFlight e clicar no botão 'Atualizar Firmware'.

	> Fazer download do firmware:
	> - https://firmware.ardupilot.org/Copter/stable/omnibusf4pro/arducopter_with_bl.hex
	> - Carregar o arquivo do firmware localmente e iniciar a atualização.


