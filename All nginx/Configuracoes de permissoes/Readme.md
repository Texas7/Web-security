## Configurações de permissões

```
> bloqueio de ip:

deny <ip>



> Permitir IPs da rede ou IPs específicos:

allow <ip/24>



>  Negar tudo ou permitir tudo:

deny all

permit all



> Anti Hotlink (permite acesso apenas utilizando url específica)

valid_referers none blocked site.com *.site.com;

if ($invalid_referer){
  return 403;
}



> Anti Hotlink em arquivos específicos:

location ~ \.(jpe?g|png|gif)${
  valid_referers none blocked site.com *.site.com;
  
  if ($invalid_referer){
    return 403;
  }
}
```

