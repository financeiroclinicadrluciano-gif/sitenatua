# Este repo NAO vai para o ar

`sitenatua` e legado. A pagina `/consultas` de `natuamedspa.com` **nao** e servida
daqui. Ela vive em:

```
~/Repos-8D/vision-build-stream/public/consultas/index.html
```

## Como isso foi medido, em 2026-08-24

```bash
curl -s "https://natuamedspa.com/consultas/" -o /tmp/live.html
cmp -s /tmp/live.html ~/Repos-8D/vision-build-stream/public/consultas/index.html && echo IGUAL
cmp -s /tmp/live.html ~/Repos-8D/sitenatua/docs/index.html && echo IGUAL
```

Producao bateu **byte a byte** com a copia do `vision-build-stream`. A copia
daqui estava **2.616 bytes atras** e nao tinha o `trackSingle` do pixel da Meta,
trabalho de 21/08 que so existe na copia viva.

## O que aconteceu, para nao se repetir

Em 24/08 apliquei tres correcoes ditadas pelo Dr. Luciano **aqui**, commitei e dei
push (commit `06e0934`). Nada mudou no site. Depois refiz tudo no arquivo certo.

O `estado_projeto_8d.sh` nunca esteve errado: ele **nao lista** este repo, e o
`00-SISTEMA/FONTES-DA-VERDADE-8D.md` ja registrava *"sitenatua, legado,
substituido pelo vision-build-stream"* desde antes. O erro foi meu: cheguei ao
arquivo por `grep -rn` em `~/Repos-8D`, e a pasta parece viva como qualquer
outra.

**Regra curta: antes de editar qualquer pagina, provar quem serve aquela URL
com `cmp` contra o HTML de producao. Nome de pasta nao e prova.**
