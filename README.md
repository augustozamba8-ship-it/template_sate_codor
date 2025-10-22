<!DOCTYPE html>
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