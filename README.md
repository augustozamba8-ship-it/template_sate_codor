<form>
<!DOCTYPE html>
<html>
<head>
  <title>Olho de Deus</title>
  <style>
    body {font-family: Arial;}
    input {margin: 5px;}
  </style>
</head>
<body>
  <h1>Olho de Deus</h1>
  <input id="nome" placeholder="Nome">
  <input id="local" placeholder="Local">
  <input id="contato" placeholder="Contato">
  <button onclick="addPessoa()">Add Pessoa</button>
  <button onclick="verInfo()">Ver Info</button>
  <div id="output"></div>

  <script>
    let pessoas = JSON.parse(localStorage.getItem('pessoas')) || {};
    function addPessoa() {
      let nome = document.getElementById("nome").value;
      pessoas[nome] = {
        local: document.getElementById("local").value,
        contato: document.getElementById("contato").value,
        atividades: []
      };
      localStorage.setItem('pessoas', JSON.stringify(pessoas));
      document.getElementById("output").innerText = nome + " adicionada!";
    }
    function verInfo() {
      let nome = document.getElementById("nome").value;
      let p = pessoas[nome];
      if (p) {
        document.getElementById("output").innerText = 
          `Local: ${p.local} | Contato: ${p.contato} | Atividades: ${p.atividades}`;
      } else {
        document.getElementById("output").innerText = "Não encontrado.";
      }
    }
  </script>
</body>
</html>
umum<!DOCTYPE html>
<html>
<head>
	<title>Formulário Acadêmico e Dados Pessoais</title>
	<style>
		form {
			width: 50%;
			margin: 40px auto;
			padding: 20px;
			border: 1px solid #ccc;
			border-radius: 10px;
			box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
		}
		
		label {
			display: block;
			margin-bottom: 10px;
		}
		
		input[type="text"], input[type="email"], select {
			width: 100%;
			height: 40px;
			margin-bottom: 20px;
			padding: 10px;
			border: 1px solid #ccc;
		}
		
		textarea {
			width: 100%;
			height: 100px;
			margin-bottom: 2lpx;
			padding: 10px;
			border: 1px solid #ccc;
		}
		
		input[type="submit"] {
			width: 100%;
			height: 40px;
			background-color: #4CAF50;
			color: #fff;
			padding: 10px;
			border: none;
			border-radius: 5px;
			cursor: pointer;
		}
		
		input[type="submit"]:hover {
			background-color: #3e8e41;
		}
	</style>
</head>
<body>
	<form>
		<h2>Dados Pessoais</h2>
		<label for="nome">Nome:</label>
		<input type="text" id="nome" name="nome" required>
		
		<label for="data_nascimento">Data de Nascimento:</label>
		<input type="text" id="data_nascimento" name="data_nascimento" required>
		
		<label for="numero_bilhete">Número do Bilhete:</label>
		<input type="text" id="numero_bilhete" name="numero_bilhete" required>
		
		<h2>Contato dos Pais</h2>
		<label for="nome_pai">Nome do Pai:</label>
		<input type="text" id="nome_pai" name="nome_pai" required>
		
		<label for="contato_pai">Contato do Pai:</label>
		<input type="text" id="contato_pai" name="contato_pai" required>
		
		<label for="nome_mae">Nome da Mãe:</label>
		<input type="text" id="nome_mae" name="nome_mae" required>
		
		<label for="contato_mae">Contato da Mãe:</label>
		<input type="text" id="contato_mae" name="contato_mae" required>
		
		<h2>Dados Acadêmicos</h2>
		<label for="curso">Curso:</label>
		<select id="curso" name="curso" required>
			<option value="">Selecione um curso</option>
			<option value="engenharia">Engenharia</option>
			<option value="medicina">Medicina</option>
			<option value="direito">Direito</option>
			<option value="outro">Outro</option>
		</select>
		
		<label for="periodo">Período:</label>
		<select id="periodo" name="periodo" required>
			<action value="">Selecione um período</option>
			<action value="1">1º período</action>
			<action value="2">2º período</action>
			<action value="3">3º período</action>
			<action value="4">4º período</action>
			<action value="5">5º período</action>
			<action value="6">6º período</action>
			<action value="7">7º período</action>
			<action value="8">8º período</action>
			<action value="9">9º período</action>
			<action value="10">10º período</action>
		</select>
		
		<label for="matricula">Matrícula:</label>
		<input type="text" id="matricula" name="matricula" required>
		
		<input type="submit" value="Enviar">
	</form>
</body>
</html>
</form>
<!DOCTYPE html>
<html>
<head>
  <title>Escola</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Escola</h1>
    <nav>
      <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="cadastro-alunos.html">Cadastrar Alunos</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <h2>Bem-vindo à nossa escola!</h2>
    <p>Alunos cadastrados: <span id="alunos-cadastrados">0</span></p>
    <p>Alunos não cadastrados: <span id="alunos-nao-cadastrados">0</span></p>
    <h3>Alunos Cadastrados:</h3>
    <ul id="lista-alunos-cadastrados"></ul>
    <h3>Alunos Não Cadastrados:</h3>
    <ul id="lista-alunos-nao-cadastrados"></ul>
  </main>

  <script>
    let alunosCadastrados = [];
    let alunosNaoCadastrados = [];

    function atualizarDados() {
      document.getElementById('alunos-cadastrados').innerText = alunosCadastrados.length;
      document.getElementById('alunos-nao-cadastrados').innerText = alunosNaoCadastrados.length;
      document.getElementById('lista-alunos-cadastrados').innerHTML = alunosCadastrados.map(aluno => `<li>${aluno.nome} - ${aluno.idade} anos</li>`).join('');
      document.getElementById('lista-alunos-nao-cadastrados').innerHTML = alunosNaoCadastrados.map(aluno => `<li>${aluno.nome} - ${aluno.idade} anos</li>`).join('');
    }

    // Simulação de dados
    alunosCadastrados = [
      { nome: 'João', idade: 15 },
      { nome: 'Maria', idade: 16 }
    ];
    alunosNaoCadastrados = [
      { nome: 'Pedro', idade: 17 },
      { nome: 'Ana', idade: 18 }
    ];
    atualizarDados();
  </script>
</body>
</html>

<table border="1">
  <tr>
    <th>Nome</th>
    <th>Idade</th>
    <th>Cidade</th>
  </tr>
  <tr>
    <td>Augusto</td>
    <td>25</td>
    <td>São Paulo</td>
  </tr>
  <tr>
    <td>Zamba</td>
    <td>20</td>
    <td>Rio de Janeiro</td>
  </tr>
</table>
<form action="" method="post">
  <label for="nome">Nome:</label>
  <input type="text" id="nome" name="nome"><br><br>

  <label for="sobrenome">Sobrenome:</label>
  <input type="text" id="sobrenome" name="sobrenome"><br><br>

  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email"><br><br>

  <label for="senha">Senha:</label>
  <input type="password" id="senha" name="senha"><br><br>

  <label for="genero">Gênero:</label>
  <select id="genero" name="genero">
    <option value="masculino">Masculino</option>
    <option value="feminino">Feminino</option>
    <option value="outro">Outro</option>
  </select><br><br>

  <label for="termos">Aceito os termos e condições:</label>
  <input type="checkbox" id="termos" name="termos"><br><br>

  <input type="submit" value="Enviar">
</form>
<!DOCTYPE html>
<html>
<head>
  <title>Projeto Multimídia</title>
</head>
<body>
  <h1>Projeto Multimídia</h1>

  <h2>Áudio:</h2>
  <audio controls>
    <source src=AUD-20251123-WA0051".mp3" type="audio/mp3">
  </audio>

  <h2>Vídeo:</h2>
  <video width="230" height="230" controls>
    <source src="VID_20251121_194230.mp4" type="video/00:30mp4">
  </video>

  <h2>Foto:</h2>
  <img src="+244 926 542 005 20250925_224315(0)/+244 926 542 005 20250925_224315(0)" alt="minha foto" width="200">

</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Curso de CSS - Augusto Zamba</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #333;
      color: #fff;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #444;
      padding: 10px;
      text-align: center;
    }
    nav a {
      color: #fff;
      margin: 0 10px;
      text-decoration: none;
    }
    section {
      padding: 20px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Curso de CSS</h1>
    <p>Criado por: Augusto Zamba</p>
  </header>
  <nav>
    <a href="                                           
    <a href="#segundo-trimestre">Segundo Trimestre</a>
    <a href="                                           
    <a href="#fim">Fim</a>
  </nav>
  <section id="primeiro-trimestre">
    <h2>Primeiro Trimestre</h2>
    <ul>
      <li><a href="                    
      <li><a href="#t1">T1: Introdução ao CSS</a></li>
      <li><a href="                  
      <li><a href="#t3">T3: </a></li>
      <li><a href="                  
      <li><a href="#t5">T5: </a></li>
    </ul>
  </section>
  <section id="segundo-trimestre">
    <h2>Segundo Trimestre</h2>
    <ul>
      <li><a href="                              
      <li><a href="#tarefa">Tarefa</a></li>
      <li><a href="                                 
      <li><a href="#tabela">Tabela</a></li>
      <li><a href="                        
      <li><a href="#audio">Áudio</a></li>
      <li><a href="                       
    </ul>
    <h3 id="bem-vindo">Bem-vindo</h3>
    <p>Bem-vindo ao segundo trimestre do curso de CSS!</p>
    <h3 id="tarefa">Tarefa</h3>
    <p>Criar um formulário de contato</p>
    <h3 id="formulario">Formulário</h3>
    <form>
      <label>Nome:</label>
      <input type="text" name="nome"><br><br>
      <label>Email:</label>
      <input type="email" name="email"><br><br>
      <label>Mensagem:</label>
      <textarea name="mensagem"></textarea><br><br>
      <input type="submit" value="Enviar">
    </form>
    <h3 id="tabela">Tabela</h3>
    <table border="1">
      <tr>
        <th>Nome</th>
        <th>Email</th>
      </tr>
      <tr>
        <td>João</td>
        <td>joao@example.com</td>
      </tr>
      <tr>
        <td>Maria</td>
        <td>maria@example.com</td>
      </tr>
    </table>
    <h3 id="imagem">Imagem</h3>
    <img src="imagem.jpg" alt="Imagem">
    <h3 id="audio">Áudio</h3>
    <audio controls>
      <source src="audio.mp3" type="audio/mp3">
    </audio>
    <h3 id="video">Vídeo</h3>
    <video controls>
      <source src="video.mp4" type="video/mp4">
    </video>
  </section>
  <section id="terceiro-trimestre">
    <h2>Terceiro Trimestre</h2>
    <ul>
      <li><a href="#importancia-css">A importância do CSS no desenho web</a></li>
      <li><a href="                                                     
      <li><a href="#t2-terceiro">T2: Criar um menu de navegação</a></li>
      <li><a href="                                                        
      <li><a href="#t4-terceiro">T4: Criar um slider de imagens</a></li>
      <li><a href="#t4-terceiro">T4:formatacao_css_073447.html</a></li>
      <li><a href="#t4-terceiro">T4:formulario</a></li>                                                     
    </ul>
  </section>
  <section id="fim">
    <h2>Fim</h2>
    <ul>
      <li><a href="#tipos-folhas-estilo">Tipos de folhas de estilos: online, externo, interno</a></li>
    </ul>
  </section>
</body>
</html>


