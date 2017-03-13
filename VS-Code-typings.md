# VS Code + intellisense

1. il servizio di intellisense per *VSCode* usa un servizio basato su _Typescript_ per generare i metadati di intellisense prima di tutto è necessario abilitare la configurazione di supporto in *VSCode* creando nella folder _root_ del progetto per il quale si vuole l'intellisense un file denominato _jsconfig.json_ in questo file va inserita la configurazione:

    {
        "compilerOptions": {
            "target": "es6",
            "module": "commonjs",
            "allowSyntheticDefaultImports": true
        },
        "exclude": [
            "node_modules",
            "bower_components",
            "jspm_packages",
            "tmp",
            "temp"
        ]
    }

  la cosa importante da notare sotto _compilerOptions_ è il *target: es6* che dice praticamente di usare la sintassi ECMA Script 6 quindi con *le lambda* anche il _module_ specifica che tipologia di _module system_ si usa

2. è necessario installare il servizio di _typings_ per installare il servizio typing è necessario lanciare lo script (_as admin_)

    npm install typings -g

  successivamente, sempre nella root di progetto è _consigliabile_ installare il _typings_ come dependency di dev

    npm install typings --save-dev

  a questo punto il typings è installato per il progetto e per la macchina a livello root

  3. è necessario installare _i typings_ per i packages che si utilizzano nella solution node (_root folder_)
  
    //facendo il caso di avere installati i pacchetti socket.io e express
    //si installano i typings con le seguenti instruzioni

    typings install dt~socket.io --save --global
    typings install dt~express --save --global


