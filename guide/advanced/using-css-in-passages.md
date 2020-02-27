# Usar CSS nas Passagens

Na grande maioria dos casos, a melhor forma de personalizar o aspeto visual da tua história é usar [a funcionalidade integrada do Chapbook][customization] ou o menu _Editar a Folha de Estilo_ no Twine. No entanto, também é possível criar código CSS específico para uma passagem, usando o modificador `[CSS]`.

```
[CSS]
.page article {
	color: green;
}

[continuado]
O texto aparecerá em verde.
```

O CSS neste modificador será aplicado globalmente — daí a razão de se usar o seletor `.page article`.

[customization]: ../customization
