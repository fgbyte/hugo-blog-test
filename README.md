# Trabajando en Hugo

primeramente hago un deploy en vercel
luego ese server crea un repo en mi github
ese repo lo clono a mi local para trabajarlo
para ver los cambios en local habro un server con hugo en esa carpeta,
en el VS-code abro un terminal inegrado sobre el archivo config.tolm
entonces pongo ```hugo serve```
esto hace q me de un link local para previsualizar los cambios

si doy ```hugo```
me crea el folder public con el site, pero no se ve el css,
esto debe ser por problemas de la url, q no se como solucionarlo

no obstante teniendo el server de vercel desplegado con hugo directamente, no necesitaria hacer un public ya que este corre con hugo

## cambiando el theme en local
creo branch develop para esto

bueno, descargando desde el method 3 pude cambiar el theme en el branch develop use el theme PaperMode

para ello tuve que descargar en zip, solo ultimo update y poner en

.github/ISSUE_TEMPLATE/config.yml -> 
``` yml 
theme: "PaperMode" 
```

ok, ahora tengo q  hacer merge con main 
- ahora hacer push to github, a ver si sale en vercel.

da error el deploy, me dice esto
```WARN 2021/10/08 17:09:28 Module "PaperMod" is not compatible with this Hugo version; run "hugo mod graph" for more information.```

por tanto hugo no pincha con vercel 😔


## Sacando a Estatico pa la pin

Tengo q sacarlo en estatico, en develop
```hugo -d docs```
ahora me voy en vivo a ver 🤞🤞,
no pincha css ni pinga
a ver si modificando el url del config, lo dejo en solo "docs"
le doy de nuevo a ```hugo -d docs``` pa crear el static
y........ yessssssssssssss, works.

ahora a hacer push de develop como esta para ponerlo en el github pages
ohh
ahora hay q poner la url del github al config = https://fernandoindesign.github.io/hugo-blog-test/
dar ```hugo -d docs``` y push
y........ boooooooooooommmm 🔥🔥🔥 stamos up

ahora lo que queda es trabajar en modo hugo serve
cuando termine hago el commit y creo el static en docs
y todo happy 😋

## Ahora ver si puedo montar el Statico en Vercel, aunque no tiene q ser necesario a no ser q sea un content private