# Json-Cidades-BR
###Segue os meus dois arquivos json com todos os Estados e os 5570 municipios, para popular dinamicamente os 
###formularios. Exemplo de uso em Nodejs
```
var estados = __dirname+'/estados.json'; var cidades = __dirname+'/cidades.json'; function jamil(id, file, 
cb){ if(id){ var linha = id - 1;
}
fs.readFile(file, 'utf8', function (err, data) { if (err) { console.log('Error: ' + err); return;
}
data = JSON.parse(data); if(!id){ cb(data);
} else {
cb(data[linha]);
}
});
}
```
###Procurar dados especificos de um estado ou cidade
```
jamil(4, estados, function(data) { console.log(data.nome);
});
```
###Mostrar a lista toda de estados ou cidades
```
jamil(0, cidades, function(data) { console.log(data);
});
```
###Os Campos retornados pelo json para Estados são: id, nome, uf Os Campos retornados pelo json para Cidades 
###são: id, nome, estado Todos os nomes estão em codificação UTF-8
Exemplo para procurar o Estado pela Cidade. 
``` 
jamil(2437, cidades, function(cid) { jamil(cid.estado, estados, 
function(est) { console.log("Estado: "+ est.nome +" , UF: "+ est.uf +" , Cidade: "+cid.nome);
}); );
```
####[Gostou? Curta a minha pagina no facebook: https://www.facebook.com/Jamilservicos](https://www.facebook.com/Jamilservicos).
