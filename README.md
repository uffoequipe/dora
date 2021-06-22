
# DORA (Drone com OmnibusF4 e RaspberryPi Atachados)

#### Resources

- ### OS: Ubuntu

### 1. Instalar a firmware ArduCopter na controladora:
- Conectar via USB a controladora ao computador.
	> Garanta que o cabo usb está bom realmente, no Linux basta usar o comando 'lsusb' e verificar se o dispositivo está listado.
- Colcar a placa em modo DFU.
	> Desconecte a placa depois conecte o cabo usb novamente com o botão de bootloader pressionado.
- Verificar se a controladora está em modo DFU com os comandos:
	>```bash
	> sudo apt install dfu-util
	> dfu-util --list
	>```

- Instalar firmware na controladora via programa CleanFlight:

	> Instalar a extensão do CleanFligt pro Chrome: 
	> - https://chrome.google.com/webstore/detail/cleanflight-configurator/enacoimjcgeinfnnnpajinjgmkahmfgb

	> Coloque o seu usuário nos grupos dialout e plugdev, para ter acesso às portas seriais do seu computador, isso também permite que o CleanFlight as acesse.
	>```bash
	>sudo usermod -aG dialout,plugdev $USER
	>```

	> Pare o serviço ModemManager caso ele esteja sendo executado.
	>```bash
	> sudo systemctl stop ModemManager.service
	>```

	> Insira essa configuração no final do arquivo **'/etc/udev/rules.d/45-stm32dfu.rules'**, se ele não existir pode criar o arquivo:
	>```bash
	> # DFU (Internal bootloader for STM32 MCUs)
	> SUBSYSTEM=="usb", ATTRS{idVendor}=="0483", ATTRS{idProduct}=="df11", MODE="0664", GROUP="plugdev"
	>```

	> Fazer flash do firmware:
	> - Abrir o CleanFlight e clicar no botão 'Atualizar Firmware'.
	> - Fazer download da firmware https://firmware.ardupilot.org/Copter/stable/omnibusf4pro/arducopter_with_bl.hex
	> - Carregar o arquivo da firmware localmente e iniciar a atualização.


