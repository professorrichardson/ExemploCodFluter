# Programação mobile 
Código  flutter para criar a primeira tela

IDE ON-LINE para rodar o Flutter (https://flutlab.io/)
###########################################################################################################
[Download Android Studio](https://developer.android.com/studio?hl=pt-br)
###########################################################################################################

Para criar uma tela de login simples no Android Studio com um título, campos de email e senha, e um botão que exibe uma mensagem ao ser clicado, siga o passo a passo abaixo:

### 1. Configurar o Projeto no Android Studio

Primeiro, crie um novo projeto no Android Studio:

1.  Abra o Android Studio e clique em "Start a new Android Studio project".
2.  Escolha a opção "Empty Activity".
3.  Dê um nome para o seu projeto (ex: `LoginApp`).
4.  Escolha a linguagem Kotlin (ou Java, se preferir) e a versão mínima do SDK (geralmente, você pode deixar o padrão).

### 2. Criar o Layout da Tela de Login

Depois de criar o projeto, você precisará configurar a interface no arquivo XML, que fica dentro de `res/layout/activity_main.xml`.

Aqui está o código XML para a tela de login:

xml

Copiar

`<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- Título da tela -->
    <TextView
        android:id="@+id/titulo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Tela de Login"
        android:textSize="24sp"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="50dp"/>

    <!-- Campo de Email -->
    <EditText
        android:id="@+id/campoEmail"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Email"
        android:inputType="textEmailAddress"
        android:layout_below="@id/titulo"
        android:layout_marginTop="30dp"
        android:padding="10dp"
        android:layout_marginLeft="20dp"
        android:layout_marginRight="20dp"/>

    <!-- Campo de Senha -->
    <EditText
        android:id="@+id/campoSenha"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Senha"
        android:inputType="textPassword"
        android:layout_below="@id/campoEmail"
        android:layout_marginTop="20dp"
        android:padding="10dp"
        android:layout_marginLeft="20dp"
        android:layout_marginRight="20dp"/>

    <!-- Botão Enviar -->
    <Button
        android:id="@+id/botaoEnviar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Enviar"
        android:layout_below="@id/campoSenha"
        android:layout_marginTop="30dp"
        android:layout_marginLeft="20dp"
        android:layout_marginRight="20dp"/>

</RelativeLayout>` 

### 3. Adicionar a Lógica no Arquivo Kotlin (MainActivity)

Agora, você precisa adicionar a lógica no arquivo `MainActivity.kt`, que vai lidar com o evento de clique no botão.

Abra o arquivo `MainActivity.kt` e insira o seguinte código:

kotlin

Copiar

`package com.example.loginapp // Altere para o nome do seu pacote

import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.EditText
import android.widget.Toast
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Referências para os campos de texto e botão
        val campoEmail: EditText = findViewById(R.id.campoEmail)
        val campoSenha: EditText = findViewById(R.id.campoSenha)
        val botaoEnviar: Button = findViewById(R.id.botaoEnviar)

        // Configuração do clique do botão
        botaoEnviar.setOnClickListener {
            val email = campoEmail.text.toString()
            val senha = campoSenha.text.toString()

            // Validar se os campos estão preenchidos
            if (email.isEmpty() || senha.isEmpty()) {
                Toast.makeText(this, "Por favor, preencha todos os campos!", Toast.LENGTH_SHORT).show()
            } else {
                // Exibir mensagem com os valores informados
                Toast.makeText(this, "Email: $email \nSenha: $senha", Toast.LENGTH_LONG).show()
            }
        }
    }
}` 

### 4. Executar o Aplicativo

Agora, para executar o aplicativo no Android Studio, siga estas etapas:

1. Use um emulador.
2.  Clique no botão "Run" (ícone de play verde) na barra de ferramentas do Android Studio.
3.  Escolha o dispositivo ou emulador onde deseja executar a aplicação.

O Android Studio irá compilar o código e instalar o aplicativo no dispositivo escolhido. Ao abrir o aplicativo, você verá a tela de login com campos para email e senha. Ao clicar no botão "Enviar", será exibida uma mensagem com o conteúdo dos campos.
