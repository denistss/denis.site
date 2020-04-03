#Javascript

###Funções em javascript
####Verificar se um número é Par ou Impar:
~~~
function ParImpar(x) {
	var calculo = x % 2;

	if (calculo == 0) {
		n = console.log('Este número é Par');
	}

	else { 
		n = console.log('Este número é Impar');
	}
	return n
}
~~~