# Instalar Mac-OS X Snow Leopard en VirtualBox

## Entorno
- Portátil con CPU Intel con soporte VT-d
- Linux Mint 17 (64bit) - basado en Ubuntu 14.04 (64bit)
- VirtualBox 4.3.20

## Pasos
1. Comprar un DVD de instalación de [Snow Leopard][1] por unos 18 euros + gastos de envío.
2. Por comodidad crear una imagen ISO del DVD original y utilizarla en vez del disco.
3. Crear una máquina virtual en virtual con las opciones siguientes
    - Name: mimaco <--poner el nombre que se quiera
    - Type: Mac OS X (64bit)
    - Version: Mac OS X 10.6 Snow Leopard (64 bit)
4. CERRAR VirtualBox
5. Añadir esto en el fichero XXXX.vbox

'''
<ExtraData>
    <ExtraDataItem name="VBoxInternal2/EfiBootArgs" value=" "/>
    <ExtraDataItem name="VBoxInternal2/SmcDeviceKey" value="ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"/>
</ExtraData>
'''

## Links
[1]: http://store.apple.com/fr/product/MC573F/A/mac-os-x-106-snow-leopard
