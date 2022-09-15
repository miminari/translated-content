---
title: Uma reintrodução ao JavaScript (Tutorial de JS)
slug: Web/JavaScript/Language_Overview
translation_of: Web/JavaScript/A_re-introduction_to_JavaScript
original_slug: Web/JavaScript/A_re-introduction_to_JavaScript
---
<h2 id="Introdução">Introdução</h2>

<p>Por que uma reintrodução? Porque <a href="/en/JavaScript" title="en/JavaScript">JavaScript</a> é conhecida como <a class="external" href="http://javascript.crockford.com/javascript.html">a mais incompreendida linguagem de programação do mundo</a>. Embora muitas vezes ridicularizada como um brinquedo, por baixo de sua simplicidade enganosa estão alguns recursos poderosos da linguagem, que agora é usado por um número incrível de aplicações de alto nível, mostrando que o conhecimento mais profundo desta tecnologia é uma habilidade importante para qualquer desenvolvedor web, mobile ou desktop. </p>

<p>É sempre bom começar com a história da linguagem. A JavaScript foi criada em 1995 por Brendan Eich, um engenheiro da Netscape, e lançada pela primeira vez com o Netscape 2 no início de 1996. Foi inicialmente chamada de LiveScript, mas logo foi rebatizada, em uma decisão de marketing malfeita, para tentar crescer sobre a popularidade da linguagem Java da Sun Microsystem - apesar das duas terem muito pouco em comum. Esta tem sido uma fonte de confusão desde então.</p>

<p>A Microsoft lançou uma versão compatível com a maior parte da linguagem, chamada de JScript, junto com o IE, três meses mais tarde. A Netscape apresentou a linguagem a Ecma International, uma organização européia de normalização, o que resultou na primeira edição do padrão ECMAScript em 1997. O padrão recebeu uma atualização significativa com o ECMAScript Edição 3 em 1999, e manteve-se praticamente estável desde então. A quarta edição foi abandonada, devido a diferenças políticas relativas à complexidade da linguagem. Muitas partes da quarta edição formam a base da nova edição ECMAScript 5, publicado em dezembro de 2009.</p>

<p>Esta estabilidade foi uma grande notícia para os desenvolvedores, pois isto proporcionou que várias implementações em JavaScript tivessem muito tempo para se firmar. Eu vou focar quase exclusivamente no dialeto da edição 3. Para que seja facil se familiarizar, vou utilizar o termo JavaScript por todo o texto.</p>

<p>Diferentemente da maioria das linguagens de programação , a linguagem JavaScript não possui o conceito de entrada e saída. Ela é projetada para funcionar como uma linguagem de script em um ambiente de terceiros, e cabe ao ambiente fornecer mecanismos para a comunicação com o mundo exterior. O ambiente de terceiros (hospedeiro) mais comum é o navegador, mas interpretadores JavaScript também pode ser encontrados no Adobe Acrobat, Photoshop, imagens SVG, Widget engine do Yahoo! , bem como ambientes de servidor, como Node.js. No entanto, a lista aqui apresentada das áreas nas quais a JavaScript é utilizada é apenas o começo. Ela também inclui bancos de dados NoSQL, como o código-fonte aberto Apache CouchDB, computadores embarcados, ou ambientes de trabalho completos, como o GNOME (um dos GUIs mais populares para os sistemas operacionais GNU / Linux) .</p>

<h2 id="Visão_Geral">Visão Geral</h2>

<p><br>
 A JavaScript é uma linguagem dinâmica orientada a objetos; tem tipos e operadores, objetos e métodos. Sua sintaxe vem das linguagens Java e C, por isso tantas estruturas dessas linguagens se aplicam a JavaScript também. Uma das principais diferenças é que o JavaScript não tem classes; em vez disso, a funcionalidade de classe é realizada por protótipos de objetos. A outra diferença principal é que as funções são objetos, dando as funções a capacidade para armazenar código executável e serem passadas como parametro para qualquer outro objeto.<br>
 <br>
 Vamos começar pelo bloco de construção de qualquer linguagem: os tipos. Programas JavaScript manipulam valores, e esses valores todos pertencem a um tipo. Tipos de JavaScript são :</p>

<ul>
 <li>    números</li>
 <li>    strings</li>
 <li>    booleanos</li>
 <li>    funções</li>
 <li>    objetos</li>
</ul>

<p>... Ops, e o "indefinido" e o "nulo"- , que parecem um pouco estranhos. E arrays (vetores), que são um tipo especial de objeto. E as datas e expressões regulares, que são objetos que você ganha de graça. E para ser tecnicamente preciso, as funções são apenas um tipo especial de objeto. Assim, a lista de tipos se parece mais com isto:</p>

<ul>
 <li>números (numbers)</li>
 <li>strings (strings)</li>
 <li>booleanos (booleans)</li>
 <li>objetos (objects)
  <ul>
   <li>funções (functions)</li>
   <li>vetores (arrays)</li>
   <li>datas (dates)</li>
   <li>expressoes regulares (regexp)</li>
  </ul>
 </li>
 <li>nulo (null)</li>
 <li>indefinido (undefined)</li>
</ul>

<p>E existem também alguns tipos para erros. As coisas são muito mais fáceis se ficarmos com a primeira lista, no entanto.</p>

<h2 id="Números">Números</h2>

<p>Números em JavaScript são "valores de precisão dupla no formato IEEE 754", de acordo com a especificação. Isto tem algumas consequências interessantes. Não existe essa coisa de inteiro em JavaScript, então você deve ser um pouco cuidadoso com seus cálculos se você está acostumado a matemática em C ou Java. Cuidado com coisas como:</p>

<pre class="eval">0.1 + 0.2 == 0.30000000000000004
</pre>

<p>Na prática, valores inteiros são tratados como inteiros de 32 bits (e são armazenados dessa forma em algumas implementações do navegador), que podem ser importantes para as operações bit a bit. Para mais detalhes, consulte <a class="external" href="http://www.hunlock.com/blogs/The_Complete_Javascript_Number_Reference">The Complete JavaScript Number Reference</a>.</p>

<p>Os <a href="/en/JavaScript/Reference/Operators/Arithmetic_Operators">operadores numéricos</a> padrões são suportados, incluindo adição, subtração, módulo (ou resto) aritmético e assim por diante. Há também um objeto embutido que eu esqueci de mencionar mais cedo chamado <a href="/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Math">Math</a> para manipular funções e constantes matemáticas mais avançadas:</p>

<pre class="brush: js">Math.sin(3.5);
var d = Math.PI * r * r;
</pre>

<p>Você pode converter uma string em um inteiro usando a função embutida <code><a href="/en/JavaScript/Reference/Global_Objects/parseInt" title="en/Core_JavaScript_1.5_Reference/Global_Functions/parseInt">parseInt()</a></code>. Ela tem um segundo parâmetro opcional para a base da conversão, parâmetro esse que você deveria sempre prover:</p>

<pre class="brush: js">&gt; parseInt("123", 10)
123
</pre>

<p>Se você quiser converter um número binário em um inteiro, basta mudar a base:</p>

<pre class="brush: js">&gt; parseInt("11", 2)
3
</pre>

<p>Similarmente, você pode fazer a conversão de números de ponto flutuante usando a função embutida <code><a href="/en/JavaScript/Reference/Global_Objects/parseFloat" title="en/JavaScript/Reference/Global Objects/parseFloat">parseFloat()</a></code> que usa a base 10 sempre, ao contrário de seu primo <a href="/en/JavaScript/Reference/Global_Objects/parseInt" title="en/JavaScript/Reference/Global Objects/parseInt"><code>parseInt()</code></a>.</p>

<p>Você também pode usar o operador unário <code>+</code> para converter valores em números:</p>

<pre>&gt; + "42"
42
</pre>

<p>Um valor especial chamado <code><a href="/en/JavaScript/Reference/Global_Objects/NaN" title="en/Core_JavaScript_1.5_Reference/Global_Properties/NaN">NaN</a></code> (sigla de "Not a Number ou Não é Número") é retornado se a string não é um valor numérico:</p>

<pre class="brush: js">&gt; parseInt("hello", 10)
NaN
</pre>

<p><code>NaN</code> é tóxico: Se você provê-lo como uma entrada para qualquer operação matemática o resultado também será <code>NaN</code>:</p>

<pre class="brush: js">&gt; NaN + 5
NaN
</pre>

<p>Você pode testar se é <code>NaN</code> usando a função embutida <code><a href="/en/JavaScript/Reference/Global_Objects/isNaN" title="en/Core_JavaScript_1.5_Reference/Global_Functions/isNaN">isNaN()</a></code>:</p>

<pre class="brush: js">&gt; isNaN(NaN)
true
</pre>

<p>JavaScript também tem os valores especiais <code><a href="/en/JavaScript/Reference/Global_Objects/Infinity" title="en/Core_JavaScript_1.5_Reference/Global_Properties/Infinity">Infinity</a></code> e <code>-Infinity</code>:</p>

<pre class="brush: js">&gt; 1 / 0
Infinity
&gt; -1 / 0
-Infinity
</pre>

<p>Você pode testar se o valor é <code>Infinity</code>, <code>-Infinity</code> e <code>NaN</code> usando a função embutida <code><a href="/en/JavaScript/Reference/Global_Objects/isFinite" title="en/Core_JavaScript_1.5_Reference/Global_Functions/isFinite">isFinite()</a></code>:</p>

<pre class="brush: js">&gt; isFinite(1/0)
false
&gt; isFinite(-Infinite)
false
&gt; isFinite(NaN)
false
</pre>

<div class="note"><strong>Nota:</strong> As funções <a href="/en/JavaScript/Reference/Global_Objects/parseInt" title="en/JavaScript/Reference/Global Objects/parseInt"><code>parseInt()</code></a> e <code><a href="/en/JavaScript/Reference/Global_Objects/parseFloat" title="en/JavaScript/Reference/Global Objects/parseFloat">parseFloat()</a></code> fazem a conversão da string até alcançarem um caracter que não é válido para o formato numérico especificado, então elas retornam o número convertido até aquele ponto. Contudo, o operador "+" simplesmente converte a string em <code>NaN</code> se tiver algum caracter inválido nela. Apenas tente por si mesmo converter a string "10.2abc" usando cada um desses métodos no console e entenderá melhor essas diferenças.</div>

<h2 id="Strings">Strings</h2>

<p>Strings em JavaScript são sequências de caracteres. Para ser mais exato, elas são sequências de <a href="/en/JavaScript/Guide/Obsolete_Pages/Unicode" title="en/Core_JavaScript_1.5_Guide/Unicode">Unicode characters</a>, em que cada um deles é representado por um número de 16-bits. Isso deveria ser uma notícia bem-vinda para aqueles que tiveram que lidar com internacionalização.</p>

<p>Se você quiser representar um único caractere, você só tem que usar uma string de tamanho 1.</p>

<p>Para obter o tamanho de uma string, acesse sua propriedade <code><a href="/en/JavaScript/Reference/Global_Objects/String/length" title="en/Core_JavaScript_1.5_Reference/Global_Objects/String/length">length</a></code>:</p>

<pre class="brush: js">&gt; "hello".length
5
</pre>

<p>Essa é nossa primeira pincelada com objetos JavaScript! Eu mencionei que strings também são objetos? De modo que elas têm métodos:</p>

<pre class="brush: js">&gt; "hello".charAt(0)
h
&gt; "hello, world".replace("hello", "goodbye")
goodbye, world
&gt; "hello".toUpperCase()
HELLO
</pre>

<h2 id="Outros_tipos">Outros tipos</h2>

<p>No JavaScript há distinção entre <code>null</code>, que é um objeto do tipo 'object' para indicar deliberadamente uma ausência de valor, do <code>undefined</code>, que é um objeto do tipo 'undefined' para indicar um valor não inicializado — isto é, que um valor não foi atribuído ainda. Vamos falar sobre variáveis depois, mas em JavaScript é possível declarar uma variável sem atribuir um valor para a mesma. Se você fizer isso, a variável será do tipo <code>undefined</code>.</p>

<p>JavaScript tem um tipo boolean, ao qual são possíveis os valores <code>true</code> e <code>false</code> (ambos são palavras-chave). Qualquer valor pode ser convertido em um boolean, de acordo com as seguintes regras:</p>

<ol>
 <li><code>false</code>, <code>0</code>, a string vazia(<code>""</code>), <code>NaN</code>, <code>null</code>, e <code>undefined</code> todos tornam-se <code>false</code></li>
 <li>todos os outros valores tornam-se <code>true</code></li>
</ol>

<p>Você pode fazer essa conversão explicitamente usando a função <code>Boolean()</code>:</p>

<pre class="brush: js">&gt; Boolean("")
false
&gt; Boolean(234)
true
</pre>

<p>Contudo, essa é uma necessidade rara, uma vez que JavaScript silenciosamente fará essa conversão quando for esperado um boolean, como em uma instrução <code>if</code>. Por isso, algumas vezes falamos simplesmente em "valores true" e "valores false" nos referindo a valores que se tornaram <code>true</code> e <code>false</code>, respectivamente, quando convertidos em boolean. Alternativamente, esses valores podem ser chamados de "truthy" (verdade/verdadeiro) e "falsy" (falso/falsidade), respectivamente.</p>

<p>Operações booleanas como <code>&amp;&amp;</code> (<em>and </em>lógico), <code style="font-style: normal; line-height: 1.5;">||</code> (<em>or </em>lógico), e <code style="font-style: normal; line-height: 1.5;">!</code> (<em>not </em>lógico) são suportadas.</p>

<h2 id="Variáveis">Variáveis</h2>

<p>Novas variáveis em JavaScript são declaradas usando a palavra-chave <code><a href="/en/JavaScript/Reference/Statements/var" title="en/Core_JavaScript_1.5_Reference/Statements/var">var</a></code>:</p>

<pre class="brush: js">var a;
var name = "simon";
</pre>

<p>Se você declarar uma variável sem atribuir qualquer valor a ela, seu tipo será <code>undefined</code>. </p>

<p>Uma diferença importante de outras linguagens como Java é que em JavaScript, blocos não tem escopo; somente funções tem escopo. De modo que se uma variável é definida usando <code>var</code> numa instrução composta (por exemplo dentro de uma estrutura de controle <code>if</code>), ela será visível por toda a função.</p>

<p>Obs: A definição de variáveis usando o let foi introduzida no ECMAScript 6. O let permite escopo de bloco, ou seja, é possível definir uma variável em um bloco <code>if</code>, e esta variável ter escopo limitado ao bloco <code>if</code>- por exemplo.</p>

<h2 id="Operadores">Operadores</h2>

<p>Operadores numéricos de JavaScript são <code>+</code>, <code>-</code>, <code>*</code>, <code>/</code> e <code>%</code> - que é o operador resto. Valores são atribuídos usando <code>=</code>, e temos também as instruções de atribuição compostas, como <code>+=</code> e <code>-=</code>. Essas são o mesmo que <code>x = x <em>operador</em> y</code>.</p>

<pre class="brush: js">x += 5
x = x + 5
</pre>

<p>Você pode usar <code>++</code> e <code>--</code> para incrementar ou decrementar respectivamente. Eles podem ser usados como operadores tanto antes como depois.</p>

<p>O <a href="/en/JavaScript/Reference/Operators/String_Operators" title="en/Core_JavaScript_1.5_Reference/Operators/String_Operators">operador</a> <code style="line-height: 1.5;"><a href="/en/JavaScript/Reference/Operators/String_Operators" style="line-height: 1.5;" title="en/Core_JavaScript_1.5_Reference/Operators/String_Operators">+</a> </code>também faz concatenação de string:</p>

<pre class="brush: js">&gt; "hello" + " world"
hello world
</pre>

<p>Se você adicionar uma string a uma número (ou outro valor) tudo será convertido em uma string primeiro. Isso talvez seja uma pegadinha para você:</p>

<pre class="brush: js">&gt; "3" + 4 + 5
345
&gt; 3 + 4 + "5"
75
</pre>

<p>Adicionar uma string em branco a algo é uma maneira melhor de fazer a conversão.</p>

<p><a href="/en/JavaScript/Reference/Operators/Comparison_Operators" title="en/Core_JavaScript_1.5_Reference/Operators/Comparison_Operators">Comparações</a> em JavaScript podem ser feitas usando <code>&lt;</code>, <code>&gt;</code>, <code>&lt;=</code> e <code>&gt;=</code>. Isso funciona tanto para strings como para números. A igualdade é um pouco menos simples. O operador igual-duplo faz a coersão de tipo se você colocar tipos diferentes, algumas vezes com resultados interessantes:</p>

<pre class="brush: js">&gt; "dog" == "dog"
true
&gt; 1 == true
true
</pre>

<p>Para evitar a coersão de tipo, use o operador igual-triplo:</p>

<pre class="brush: js">&gt; 1 === true
false
&gt; true === true
true
</pre>

<p>Temos também os operadores <code>!=</code> e <code>!==</code> .</p>

<p>JavaScript também tem <a href="/en/JavaScript/Reference/Operators/Bitwise_Operators" title="en/Core_JavaScript_1.5_Reference/Operators/Bitwise_Operators">operações de bit-a-bit</a>. Se quiser usá-las, elas estarão lá.</p>

<h2 id="Estruturas_de_Controle">Estruturas de Controle</h2>

<p>JavaScript tem um conjunto de estruturas de controle similar à outras linguagens na família do C. Instruções condicionais são suportadas pelo <code>if</code> e <code>else</code>; você pode encadeá-los se quiser:</p>

<pre class="brush: js">var name = "kittens";
if (name == "puppies") {
  name += "!";
} else if (name == "kittens") {
  name += "!!";
} else {
  name = "!" + name;
}
name == "kittens!!"
</pre>

<p>JavaScript tem as estruturas de repetição com os laços <code>while</code> e <code>do-while</code>. O primeiro é bom para repetições básicas; o segundo é para os casos em que você queira que o corpo da repetição seja executado pelo menos uma vez:</p>

<pre class="brush: js">while (true) {
  // an infinite loop!
}

var input;
do {
  input = get_input();
} while (inputIsNotValid(input))
</pre>

<p>O laço <code style="font-style: normal;">for</code> do JavaScript é o mesmo que no C e Java: ele lhe permite prover as informações para o seu laço em uma única linha.</p>

<pre class="brush: js">for (var i = 0; i &lt; 5; i++) {
  // Will execute 5 times
}
</pre>

<p>Os operadores <code>&amp;&amp;</code> e <code>||</code>  usam a lógica de curto-circuito, o que quer dizer que, o segundo operando ser executado dependerá do primeiro operando. Isso é útil para checagem de objetos null antes de acessar seus atributos:</p>

<pre class="brush: js">var name = o &amp;&amp; o.getName();
</pre>

<p>Ou para configuração de valores-padrões:</p>

<pre class="brush: js">var name = otherName || "default";
</pre>

<p>JavaScript tem um operador ternário para expressões condicionais:</p>

<pre class="brush: js">var allowed = (age &gt; 18) ? "yes" : "no";
</pre>

<p>A instrução switch pode ser usada para múltiplas ramificações baseadas em um número ou uma string:</p>

<pre class="brush: js">switch(action) {
    case 'draw':
        drawit();
        break;
    case 'eat':
        eatit();
        break;
    default:
        donothing();
}
</pre>

<p>Se você não adicionar a instrução <code>break</code>, a execução irá "cair" no próximo nível. Isso é algo que raramente vai querer fazer — de fato vale mais a pena colocar um comentário especificando essa "queda" para o próximo nível, pois isso o ajudará na hora de fazer a depuração de seu código:</p>

<pre class="brush: js">switch(a) {
    case 1: // queda
    case 2:
        eatit();
        break;
    default:
        donothing();
}
</pre>

<p>A cláusula default é opcional. Se quiser, pode colocar expressões tanto no switch como nos cases; Comparações acontecem entre os dois usando o operador <code>===</code>:</p>

<pre class="brush: js">switch(1 + 3) {
    case 2 + 2:
        yay();
        break;
    default:
        neverhappens();
}
</pre>

<h2 id="Objetos">Objetos</h2>

<p>Objetos JavaScript são simplesmente coleções de pares nome-valor. Como tal, eles são similares à:</p>

<ul>
 <li>Dicionários em Python</li>
 <li>Hashes em Perl e Ruby</li>
 <li>Hash tables em C e C++</li>
 <li>HashMaps em Java</li>
 <li>Vetores associativos em PHP</li>
</ul>

<p>Esse tipo de estrutura de dados é largamente utilizada, o que atesta sua versatilidade. Uma vez que tudo em JavaScript é um objeto (tipos básicos principais), qualquer programa JavaScript naturalmente envolve uma grande quantidade de buscas em tabelas hash, o que é algo bom, pois elas são bem rápidas!</p>

<p>A parte "name" é uma string JavaScript, enquanto o valor pode ser qualquer valor JavaScript — incluindo mais objetos. Isso permite que você construa estruturas de dados de qualquer complexidade.</p>

<p>Há basicamente duas formas de criar um objeto vazio:</p>

<pre class="brush: js">var obj = new Object();
</pre>

<p>e:</p>

<pre class="brush: js">var obj = {};
</pre>

<p>Elas são semanticamente equivalentes; a segunda forma é chamada de sintaxe de objeto literal e é mais conveniente. Essa sintaxe é também o coração do formato JSON e deveria ser sempre preferida.</p>

<p>Uma vez criada, as propriedades de um objeto podem novamente ser acessadas de uma das seguintes formas:</p>

<pre class="brush: js">obj.name = "Simon";
var name = obj.name;
</pre>

<p>E...</p>

<pre class="brush: js">obj["name"] = "Simon";
var name = obj["name"];
</pre>

<p>Estas também são semânticamente equivalentes. A segunda forma tem a vantagem de que o valor da chave é passado através de uma string, que pode ser calculada em tempo de execução, muito embora esse método previna o uso de alguns mecanismos tais como a otimização e a minificação. Outra vantagem é a possibilidade de se atribuir <a href="/en/JavaScript/Reference/Reserved_Words" title="en/Core_JavaScript_1.5_Reference/Reserved_Words">palavras-reservadas</a> aos nomes das propriedades:</p>

<pre class="brush: js">obj.for = "Simon"; // Erro de sintaxe, pois 'for' é uma palavra reservada
obj["for"] = "Simon"; // Funciona bem
</pre>

<p>A sintaxe de objeto literal pode ser usada para inicializar completamente um objeto:</p>

<pre class="brush: js">var obj = {
    name: "Carrot",
    "for": "Max",
    details: {
        color: "orange",
        size: 12
    }
}
</pre>

<p>O acesso aos atributos podem ser encadeados:</p>

<pre class="brush: js">&gt; obj.details.color
orange
&gt; obj["details"]["size"]
12
</pre>

<h2 id="Vetores">Vetores</h2>

<p>Vetores em JavaScript são, de fato, um tipo especial de objeto. Eles funcionam de forma muito similar à objetos regulares (propriedades numéricas podem naturalmente ser acessadas somente usando a sintaxe [], colchetes ), porém eles tem uma propriedade mágica chamada '<code>length</code>'. Ela sempre é o maior índice de um vetor mais 1.</p>

<p>A forma tradicional de se criar um vetor em JavaScript é a seguinte:</p>

<pre class="brush: js">&gt; var a = new Array();
&gt; a[0] = "dog";
&gt; a[1] = "cat";
&gt; a[2] = "hen";
&gt; a.length
3
</pre>

<p>Existe uma notação mais conveniente usando um vetor literal:</p>

<pre class="brush: js">&gt; var a = ["dog", "cat", "hen"];
&gt; a.length
3
</pre>

<p>Deixar uma vírgula à direita no final de um vetor literal gerará inconsistência entre os navegadores, portanto não faça isso.</p>

<p>Note que <code>array.length</code> não é necessariamente o número de itens em um vetor. Considere o seguinte:</p>

<pre class="brush: js">&gt; var a = ["dog", "cat", "hen"];
&gt; a[100] = "fox";
&gt; a.length
101
</pre>

<p>Lembre-se — o tamanho de um vetor é o maior índice mais 1.</p>

<p>Se você fizer referência a um índice de vetor inexistente, obterá um <code>undefined</code>:</p>

<pre class="brush: js">&gt; typeof a[90]
undefined
</pre>

<p>Você pode iterar sobre um vetor da seguinte forma:</p>

<pre class="brush: js">for (var i = 0; i &lt; a.length; i++) {
    // Faça algo com a[i]
}
</pre>

<p>Isso é um pouco ineficaz visto que você está procurando a propriedade length uma vez a cada iteração. Uma melhoria poderia ser:</p>

<pre class="brush: js">for (var i = 0, len = a.length; i &lt; len; i++) {
    // Faça algo com a[i]
}
</pre>

<p>Uma forma mais elegante ainda poderia ser:</p>

<pre class="brush: js">for (var i = 0, item; item = a[i++];) {
    // Faça algo com item
}
</pre>

<p>Aqui nós estamos declarando duas variáveis. A atribuição na parte do meio do laço <code>for</code> é também testada — se for verdadeira, o laço continuará. Uma vez que o <code>i</code> é incrementado toda vez, os itens do array serão atribuídos a variável item sequencialmente. A iteração é finalizada quando item "falsy" é encontrado (tal como o <code>undefined</code>, false ou zero).</p>

<p>Note que esse truque só deveria ser usado em vetores que você sabe não conter valores "falsy" (vetores de objeto ou nós <a href="/en/DOM" title="en/DOM">DOM</a> por exemplo). Se você iterar sobre dados numéricos que possam ter o 0 ou sobre dados string que possam ter uma string vazia, você deveria usar a segunda forma como alternativa.</p>

<p>Uma outra forma de iterar é usar o laço <code><a href="/en/JavaScript/Reference/Statements/for...in" title="en/Core_JavaScript_1.5_Reference/Statements/for...in">for...in</a></code>. Note que se alguém adicionou novas propriedades ao <code>Array.prototype</code>, elas também podem ser iteradas usando este laço:</p>

<pre class="brush: js">for (var i in a) {
  // Do something with a[i]
}
</pre>

<p>Se quiser adicionar um item a um vetor, simplesmente faça desse jeito:</p>

<pre class="brush: js">a[a.length] = item;                 // é o mesmo que a.push(item);
</pre>

<p>Vetores vem com vários métodos:</p>

<table style="height: 124px; width: 598px;">
 <thead>
  <tr>
   <th scope="col">Nome do método</th>
   <th scope="col">Descrição</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>a.toString()</code></td>
   <td>Retorna uma string com o toString()de cada elemento separado por vírgulas.</td>
  </tr>
  <tr>
   <td><code>a.toLocaleString()</code></td>
   <td>Retorna uma string com o toLocaleString()de cada elemento separado por vírgulas.</td>
  </tr>
  <tr>
   <td><code>a.concat(item[, itemN])</code></td>
   <td>Retorna um novo vetor com os itens adicionados nele.</td>
  </tr>
  <tr>
   <td><code>a.join(sep)</code></td>
   <td>Converte um vetor em uma string com os valores do vetor separados pelo valor do parâmetro sep</td>
  </tr>
  <tr>
   <td><code>a.pop()</code></td>
   <td>Remove e retorna o último item.</td>
  </tr>
  <tr>
   <td><code>a.push(item[, itemN])</code></td>
   <td><code>Push</code> adiciona um ou mais itens ao final.</td>
  </tr>
  <tr>
   <td><code>a.reverse()</code></td>
   <td>Reverte o vetor.</td>
  </tr>
  <tr>
   <td><code>a.shift()</code></td>
   <td>Remove e retorna o primeiro item.</td>
  </tr>
  <tr>
   <td><code>a.slice(start, end)</code></td>
   <td>Retorna um sub-vetor.</td>
  </tr>
  <tr>
   <td><code>a.sort([cmpfn])</code></td>
   <td>Prover uma função opcional para fazer a comparação.</td>
  </tr>
  <tr>
   <td><code>a.splice(start, delcount[, itemN])</code></td>
   <td>Permite que você modifique um vetor por apagar uma seção e substituí-lo com mais itens.</td>
  </tr>
  <tr>
   <td><code>a.unshift([item])</code></td>
   <td>Acrescenta itens ao começo do vetor.</td>
  </tr>
 </tbody>
</table>

<h2 id="Funções">Funções</h2>

<p>Junto com objetos, funções são os componentes principais para o entendimento do JavaScript. A função mais básica não poderia ser mais simples:</p>

<pre class="brush: js">function add(x, y) {
    var total = x + y;
    return total;
}
</pre>

<p>Isso demonstra tudo o que há para se saber sobre funções básicas. Uma função JavaScript pode ter 0 ou mais parâmetros declarados. O corpo da função pode conter tantas instruções quantas quiser e pode declarar suas próprias variáveis que são de escopo local àquela função. A instrução <code>return</code> pode ser usada para retornar um valor em qualquer parte da função, finalizando a função. Se nenhuma instrução de retorno for usada (ou um retorno vazio sem valor), o JavaScript retorna <code>undefined</code>.</p>

<p>Os parâmetros nomeados se parecem mais com orientações do que com outra coisa. Você pode chamar a função sem passar o parâmetro esperado, nesse caso eles receberão o valor <code>undefined</code>.</p>

<pre class="brush: js">&gt; add()
NaN // Você não pode executar adição em undefined
</pre>

<p>Você também pode passar mais argumentos do que a função está esperando:</p>

<pre class="brush: js">&gt; add(2, 3, 4)
5 // adicionado os dois primeiros; 4 foi ignorado
</pre>

<p>Pode parecer um pouco bobo, mas no corpo da função você tem acesso a uma variável adicional chamada <a href="/en/JavaScript/Reference/Functions_and_function_scope/arguments" title="En/Core_JavaScript_1.5_Reference/Functions_and_function_scope/arguments"><code>arguments</code></a>, que é um objeto parecido com um vetor que contém todos os valores passados para a função. Vamos rescrever a função add para tomarmos tantos valores quanto quisermos:</p>

<pre class="brush: js">function add() {
    var sum = 0;
    for (var i = 0, j = arguments.length; i &lt; j; i++) {
        sum += arguments[i];
    }
    return sum;
}

&gt; add(2, 3, 4, 5)
14
</pre>

<p>Isso realmente não é muito mais útil do que escrever <code>2 + 3 + 4 + 5</code>. Vamos criar uma função para calcular média:</p>

<pre class="brush: js">function avg() {
    var sum = 0;
    for (var i = 0, j = arguments.length; i &lt; j; i++) {
        sum += arguments[i];
    }
    return sum / arguments.length;
}
&gt; avg(2, 3, 4, 5)
3.5
</pre>

<p>Isso é muito útil, mas introduz um novo problema. A função <code>avg()</code> precisa de uma lista de argumentos separados por vírgula — mas e se o que quiser for procurar a média de um vetor? Você poderia apenas rescrever a função da seguinte forma:</p>

<pre class="brush: js">function avgArray(arr) {
    var sum = 0;
    for (var i = 0, j = arr.length; i &lt; j; i++) {
        sum += arr[i];
    }
    return sum / arr.length;
}
&gt; avgArray([2, 3, 4, 5])
3.5
</pre>

<p>Porém, seria legal se pudéssemos reusar a função que já tínhamos criado. Felizmente, JavaScript lhe permite chamar a função, e chamá-la com um conjunto arbitrário de argumentos, usando o método <a href="/en/JavaScript/Reference/Global_Objects/Function/apply" title="en/Core_JavaScript_1.5_Reference/Global_Objects/Function/apply"><code>apply()</code></a> presente em qualquer objeto função.</p>

<pre class="brush: js">&gt; avg.apply(null, [2, 3, 4, 5])
3.5
</pre>

<p>O segundo argumento do <code>apply()</code> é o vetor para usar como argumento; o primeiro será discutido mais tarde. Isso enfatiza o fato que funções também são objetos.</p>

<p>JavaScript lhe permite criar funções anônimas.</p>

<pre class="brush: js">var avg = function() {
    var sum = 0;
    for (var i = 0, j = arguments.length; i &lt; j; i++) {
        sum += arguments[i];
    }
    return sum / arguments.length;
}
</pre>

<p>Isso é semanticamente equivalente a forma <code>function avg()</code>. É extremamente poderoso como ele lhe permite colocar a definição completa de uma função em qualquer lugar, que você normalmente poria uma expressão. Isso lhe permite todo tipo de truques engenhosos. Aqui está uma maneira de "esconder" algumas variáveis locais — como escopo de bloco em C:</p>

<pre class="brush: js">&gt; var a = 1;
&gt; var b = 2;
&gt; (function() {
    var b = 3;
    a += b;
})();
&gt; a
4
&gt; b
2
</pre>

<p>JavaScript lhe permite chamar funções recursivamente. Isso é particularmente útil quando estamos lidando com estruturas de árvore, como quando estavamos navegando no <a href="/en/DOM" title="en/DOM">DOM</a>.</p>

<pre class="brush: js">function countChars(elm) {
    if (elm.nodeType == 3) { // TEXT_NODE
        return elm.nodeValue.length;
    }
    var count = 0;
    for (var i = 0, child; child = elm.childNodes[i]; i++) {
        count += countChars(child);
    }
    return count;
}
</pre>

<p>Isso destaca um problema potencial com funções anônimas: Como chamá-las recursivamente se elas não tem um nome? JavaScript lhe permite nomear expressões de função para isso. Você pode usar EFIIs nomeadas (Expressões Funcionais Imediatamente Invocadas), conforme abaixo:</p>

<pre class="brush: js">var charsInBody = (function counter(elm) {
    if (elm.nodeType == 3) { // TEXT_NODE
        return elm.nodeValue.length;
    }
    var count = 0;
    for (var i = 0, child; child = elm.childNodes[i]; i++) {
        count += counter(child);
    }
    return count;
})(document.body);
</pre>

<p>O nome provido para a função anônima conforme acima só é (ou no mínimo só deveria ser) visível ao escopo da própria função. Isso tanto permite que mais otimizações sejam feitas pela engine como deixa o código mais legível.</p>

<h2 id="Objetos_Personalizados">Objetos Personalizados</h2>

<div class="note"><strong>Nota:</strong> Para uma discursão mais detalhada de programação orientada a objetos em JavaScript, veja <a href="/en/JavaScript/Introduction_to_Object-Oriented_JavaScript" title="https://developer.mozilla.org/en/Introduction_to_Object-Oriented_JavaScript">Introdução a JavaScript Orientado a Objeto</a>.</div>

<p>Na clássica Programação Orientada a Objetos, objetos são coleções de dados e métodos que operam sobre esses dados. JavaScript é uma linguagem baseada em protótipos que não contém a estrutura de classe, como tem em C++ e Java. (Algumas vezes isso é algo confuso para o programador acostumado a linguagens com estrutura de classe). Em vez disso, JavaScript usa funções como classes. Vamos considerar um objeto pessoa com os campos primeiro e último nome. Há duas formas em que o nome talvez possa ser exibido: como "primeiro nome segundo nome" ou como "último nome, primeiro nome". Usando as funções e objetos que discutimos anteriormente, aqui está uma forma de fazer isso:</p>

<pre class="brush: js">function makePerson(first, last) {
    return {
        first: first,
        last: last
    }
}
function personFullName(person) {
    return person.first + ' ' + person.last;
}
function personFullNameReversed(person) {
    return person.last + ', ' + person.first
}
&gt; s = makePerson("Simon", "Willison");
&gt; personFullName(s)
Simon Willison
&gt; personFullNameReversed(s)
Willison, Simon
</pre>

<p>Isso funciona, mas é muito feio. Você termina com dúzias de funções em seu escopo global. O que nós realmente precisamos é uma forma de anexar uma função a um objeto. Visto que funções são objetos, isso é fácil:</p>

<pre class="brush: js">function makePerson(first, last) {
    return {
        first: first,
        last: last,
        fullName: function() {
            return this.first + ' ' + this.last;
        },
        fullNameReversed: function() {
            return this.last + ', ' + this.first;
        }
    }
}
&gt; s = makePerson("Simon", "Willison")
&gt; s.fullName()
Simon Willison
&gt; s.fullNameReversed()
Willison, Simon
</pre>

<p>Há algo aqui que não havíamos visto anteriormente: a palavra-chave '<code><a href="/en/JavaScript/Reference/Operators/this" title="en/Core_JavaScript_1.5_Reference/Operators/Special_Operators/this_Operator">this</a></code>'. Usada dentro de uma função, '<code>this</code>' refere-se ao objeto corrente. O que aquilo de fato significa é especificado pelo modo em que você chamou aquela função. Se você chamou-a usando <a href="/en/JavaScript/Reference/Operators/Member_Operators" title="en/Core_JavaScript_1.5_Reference/Operators/Member_Operators">notação ponto ou notação colchete</a> em um objeto, aquele objeto torna-se '<code>this</code>'. Se a notação ponto não foi usada pela chamada, '<code>this</code>' refere-se ao objeto global. Isso é uma frequente causa de erros. Por exemplo:</p>

<pre class="brush: js">&gt; s = makePerson("Simon", "Willison")
&gt; var fullName = s.fullName;
&gt; fullName()
undefined undefined
</pre>

<p>Quando chamamos <code>fullName()</code>, '<code>this</code>' está ligado ao objeto global. Visto que não há variáveis globais chamadas <code>first</code> ou <code>last</code> obtemos <code>undefined</code> para cada um.</p>

<p>Podemos tirar vantagem da palavra chave '<code>this</code>' para melhorar nossa função <code>makePerson</code>:</p>

<pre class="brush: js">function Person(first, last) {
    this.first = first;
    this.last = last;
    this.fullName = function() {
        return this.first + ' ' + this.last;
    }
    this.fullNameReversed = function() {
        return this.last + ', ' + this.first;
    }
}
var s = new Person("Simon", "Willison");
</pre>

<p>Nós introduzimos uma outra palavra-chave: '<code><a href="/en/JavaScript/Reference/Operators/new" title="en/Core_JavaScript_1.5_Reference/Operators/Special_Operators/new_Operator">new</a></code>'. <code>new</code> é fortemente relacionada a '<code>this</code>'. O que ele faz é criar um novo objeto vazio, e então chamar a função especificada com '<code>this</code>' para atribuir aquele novo objeto. Funções que são desenhadas para ser chamadas pelo '<code>new</code>' são chamadas de funções construtoras. Uma prática comum é capitular  essas funções como um lembrete de chamá-las com o <code>new</code>.</p>

<p>Nossos objetos pessoa estão ficando melhor mas ainda existem algumas arestas feias. Toda vez que criamos um objeto pessoa, criamos duas marcas de nova função dentro dele — não seria melhor se este código fosse compartilhado?</p>

<pre class="brush: js">function personFullName() {
    return this.first + ' ' + this.last;
}
function personFullNameReversed() {
    return this.last + ', ' + this.first;
}
function Person(first, last) {
    this.first = first;
    this.last = last;
    this.fullName = personFullName;
    this.fullNameReversed = personFullNameReversed;
}
</pre>

<p>Assim está melhor: estamos criando as funções de método apenas uma vez, e atribuimos referências para elas dentro do construtor. Podemos fazer algo melhor do que isso? A resposta é sim:</p>

<pre class="brush: js">function Person(first, last) {
    this.first = first;
    this.last = last;
}
Person.prototype.fullName = function() {
    return this.first + ' ' + this.last;
}
Person.prototype.fullNameReversed = function() {
    return this.last + ', ' + this.first;
}
</pre>

<p><code>Person.prototype</code> é um objeto compartilhado por todas as instâncias de <code>Person</code>. Este forma parte da cadeia de buscas (que tem um nome especial, cadeia de protótipos ou "prototype chain"): toda a vez que você tentar acessar uma propriedade de <code>Person</code> que não está configurada, Javascript irá verificar em <code>Person.prototype</code> para ver se esta propriedade existe por lá. Como resultado, qualquer coisa atribuída à <code>Person.prototype</code> torna-se disponível para todas as instâncias deste construtor, através do objeto <code>this</code>.</p>

<p>Esta é uma ferramenta incrivelmente poderosa. JavaScript permite a você modificar algo prototipado em qualquer momento no seu programa. Isto significa que você pode adicionar métodos extras para objetos pré-existentes, em tempo de execução:</p>

<pre class="brush: js">&gt; s = new Person("Simon", "Willison");
&gt; s.firstNameCaps();
TypeError on line 1: s.firstNameCaps is not a function
&gt; Person.prototype.firstNameCaps = function() {
    return this.first.toUpperCase()
}
&gt; s.firstNameCaps()
SIMON
</pre>

<p>Curiosamente, você pode também adicionar coisas para o protótipo de objetos built-in de Javascript. Vamos adicionar um método para <code>String</code> que retorna a string invertida:</p>

<pre class="brush: js">&gt; var s = "Simon";
&gt; s.reversed()
TypeError on line 1: s.reversed is not a function
&gt; String.prototype.reversed = function() {
    let start = 0, end = this.length - 1
    result = new Array(this.length)
    while(start &lt;= end) {
      result[start] = this[end]
      result[end] = this[start]
      start++, end--
    }
    return result.join('')
}
&gt; s.reversed()
nomiS
</pre>

<p>Nosso novo método funciona inclusive em string literais!</p>

<pre class="brush: js">&gt; "This can now be reversed".reversed()
desrever eb won nac sihT
</pre>

<p>Como antes mencionado, o protótipo forma parte de uma cadeia. A raiz dessa cadeia é  <code>Object.prototype</code>, dos quais inclui o método <code>toString()</code> — este é o método que é chamado quando você tenta representar um objeto como uma string. Isto é útil para depurar os nossos objetos <code>Person</code>:</p>

<pre class="brush: js">&gt; var s = new Person("Simon", "Willison");
&gt; s
[object Object]
&gt; Person.prototype.toString = function() {
    return '&lt;Person: ' + this.fullName() + '&gt;';
}
&gt; s
&lt;Person: Simon Willison&gt;
</pre>

<p>Lembra como <code>avg.apply()</code> tinha um primeiro argumento null? Nós podemos revisitar isto, agora. O primeiro argumento para <code>apply()</code> é o objeto que deve ser tratado como '<code>this</code>'. Por exemplo, aqui está uma implementação trivial de '<code>new</code>':</p>

<pre class="brush: js">function trivialNew(constructor, ...args) {
    var o = {}; // Create an object
    constructor.apply(o, args);
    return o;
}
</pre>

<p>Isto não é exatamente uma réplica de <code>new</code> porque não configura a cadeia de protótipos. <code>apply()</code> é difícil de ilustrar — não é algo que você usa com frequência, mas é útil conhecer a respeito. No código acima, <code>...args</code> é chamado de "<a href="/pt-BR/docs/Web/JavaScript/Reference/Functions/rest_parameters">argumentos rest</a>" — como o nome indica, isto contém o restante dos parâmetros.</p>

<p>Ao chamar</p>

<pre class="brush: js">var bill = trivialNew(Person, 'Willian', 'Orange');</pre>

<p>é equivalente a</p>

<pre class="brush: js">var bill = new Person('Willian', 'Orange');</pre>

<p><code>apply()</code> tem uma função irmã de nome <a href="/en/JavaScript/Reference/Global_Objects/Function/call" title="en/Core_JavaScript_1.5_Reference/Global_Objects/Function/call"><code>call</code></a>, que novamente permite você configurar o '<code>this</code>' mas toma uma lista expandida de argumentos, ao invés de um array.</p>

<pre class="brush: js">function lastNameCaps() {
    return this.last.toUpperCase();
}
var s = new Person("Simon", "Willison");
lastNameCaps.call(s);
// Is the same as:
s.lastNameCaps = lastNameCaps;
s.lastNameCaps();
</pre>

<h2 id="Funções_Internas">Funções Internas</h2>

<p>Em JavaScript é permitido declarar uma função dentro de outras funções. Nós já vimos isso antes, com uma versão preliminar da função <code>makePerson()</code>. Um detalhe importante sobre funções aninhadas em JavaScript é que elas podem acessar as variáveis do escopo das funções parente:</p>

<pre class="brush: js"><code>function parentFunc() {
  var a = 1;

  function nestedFunc() {
    var b = 4; // parentFunc can't use this
    return a + b;
  }
  return nestedFunc(); // 5
}</code></pre>

<p>Isto permite um compromisso maior de utilidade ao escrever um código de melhor mantenibilidade. Se uma função depende de uma ou mais funções que não são úteis para outras parte do seu código, você pode aninhar estas funções utilitárias dentro da função que será chamada. Isto mantém o número de funções que estão no escopo global baixo, o que é sempre uma boa coisa.</p>

<p>Isto é também um ótimo contador de atração de variáveis globais. Quando se escreve um código complexo, é sempre tentador usar as variáveis globais para compartilhar valores entre múltiplas funções  — do qual leva a um código que é difícil de manter. Funções aninhadas podem compartilhar variáveis em seus parentes, então você pode usar este mecanismo para acoplar e juntar funções, quando isto fizer sentido, sem poluir o seu "namespace" global — 'globais locais' se preferir. Esta técnica deve ser usada com cautela, mas é uma habilidade a se ter.</p>

<h2 id="Clausuras_Closures">Clausuras (Closures)</h2>

<p>Isto nos leva a uma das abstrações mais poderosas que JavaScript tem a oferecer — mas também a mais potencionalmente confusa. O que isto faz?</p>

<pre class="brush: js">function makeAdder(a) {
  return function(b) {
    return a + b;
  };
}
var x = makeAdder(5);
var y = makeAdder(20);
x(6); // ?
y(7); // ?</pre>

<p>O nome da função <code>makeAdder</code> já diz tudo: ela cria novas funções 'adder', na qual, quando chamada com um argumento, adiciona o argumento com a que foi criada.</p>

<p>O que está acontecendo aqui é muito parecido com o que estava acontencedo com as funções internas vistas anterioremente: uma função definida dentro de uma outra função tem acessso às variáveis da função de fora. A única diferença aqui é que a função de fora retornou e, como consequência do senso comum, deve dizer que todas as variáveis locais não existem mais. Mas elas <em>ainda</em> existem — caso contrário a função adicionadora não seria capaz de funcionar. Mais ainda, há duas "cópias" diferentes de variáveis locais para <code>makeAdder</code> — uma na qual o <code>a</code> é 5 e a outra na qual <code>a</code> é 20.  Então, o resultado dessas chamadas de funções é o seguinte:</p>

<pre class="brush: js">x(6) // returns 11
y(7) // returns 27
</pre>

<p>Eis o que acontece na verdade: sempre que o JavaScript executa uma função, um objeto de 'escopo' é criado para guardar as variáveis locais criadas dentro desta função. Ela é inicializada com quaisquer variáveis passadas como parâmetros da função. Isto é similar ao objeto global, em que todas as variáveis globais e funções vivem, mas com algumas diferenças importantes: primeiro, um novo objeto de escopo é criado toda a vez que uma função começa a executar, e segundo, diferente do objeto global (que nos navegadores é acessado com <code>window</code>) estes objetos não podem ser diretamente acessados através do seu código JavaScript. Não há nenhum mecanismo para iterar sobre as propriedades do escopo corrente do objeto, por exemplo.</p>

<p>Então, quando <code>makeAdder</code> é chamado, um objeto de escopo é criado com uma única propriedade: <code>a</code>, a qual é o argumento passado para a função <code>makeAdder</code>. <code>makeAdder</code> então retorna uma nova função criada. Normalmente o coletor de lixo de JavaScript poderia limpar o objeto de escopo criado para <code>makeAdder</code> neste ponto, mas a função de retorno mantém uma referência ao objeto de escopo. Como resultado, o objeto de escopo não será coletado como lixo até que não haja mais referências para função objeto que <code>makeAdder</code> retornou.</p>

<p>Objetos de escopo formam uma cadeia chamada de cadeia de escopos, similar a cadeia de protótipos usadas no sistema de objetos de JavaScript.</p>

<p>Uma clausura é a combinação de uma função e o objeto de escopo na qual é criado. Clausuras permitem você guardar estado — de tal forma, elas podem ser frequentemente utilizadas no lugar de objetos.</p>