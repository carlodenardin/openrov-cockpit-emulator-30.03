# OpenROV Cockpit Emulator 30.03

## Requisiti
1. Ubuntu 18.04 LTS
2. Node 8.17
3. ffmpeg
4. build-essential
5. mjpg-streamer


## Comandi
1. Clonare la respository openrov-cockpit
```
git clone https://github.com/OpenROV/openrov-cockpit.git
```
2. Spostarsi all'interno della cartella openrov-cockpit
```
cd openrov-cockpit
```
3. Selezionare il ramo corrispondente alla versione 30.03
```
git checkout 7d3cebf
```
4. Installare le librerie necessarie
```
npm install
```

## Modifiche
1. Nel file PluginLoader.js in openrov-cockpit/src/lib modificare la linea 32
```
path.existsSync(..) -> fs.existsSync(..)
```
2. Nel file OpeROVArduinoFirmwareController in openrov-cockpit/src/lib modificare la linea 22
```
path.existsSync(..) -> fs.existsSync(..)
```

## Lanciare l'emulazione
1. Eseguire il comando
```
USE_MOCK=true DEV_MODE=true HARDWARE_MOCK=true MOCK_VIDEO_TYPE=MJPEG MOCK_VIDEO_HARDWARE=true configfile='/tmp/rovconfig.json' pluginsDownloadDirectory='/tmp/plugins' env plugins__ui-manager__selectedUI='classic-ui'  node src/cockpit.js
```
2. Aprire browser (testato su chrome) e collegarsi alla porta locale 8080 (localhost:8080)
![emulatore](https://github.com/denardincarlo/openrov-cockpit-emulator-30.03/blob/main/emulatore.png)
![emulatore](https://github.com/denardincarlo/openrov-cockpit-emulator-30.03/blob/main/CambioTema1.png)
