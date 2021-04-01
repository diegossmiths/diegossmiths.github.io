# diegossmiths.gitlab.com

Meu pequeno jardim nesse mundo virtual.

## Instalação

Será necessário a instalação das seguintes dependências:
```
ruby-full build-essential zlib1g-dev
```

É recomendado a instalação das gems em um diretório oculto na pasta de usuário:
Para isso execute os seguintes comandos no terminal bash
```bash
echo '' >> ~/.bashrc
echo '# Install Ruby Gems to ~/.gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/.gems"' >> ~/.bashrc
echo 'export PATH="$HOME/.gems/bin:$PATH"' >> ~/.bashrc
echo '' >> ~/.bashrc
source ~/.bashrc
```

Instale o Jekyll e o bundler. No terminal bash digite:
```bash
gem install jekyll bundler
```

Instale as gems digitando no terminal:
```bash
bundle install
```

Compile e crie o servidor localmente com o comando bash:
```bash
bundle exec jekyll serve --host 0.0.0.0
```

Com este comando o site estará disponível em http://0.0.0.0:4000/ na sua máquina e poderá ser acessado por outras máquinas usando o seu endereço de IP na rede local através da porta 4000. Isso facilita o teste em outras máquinas e em sistemas móveis.

Por padrão o tema não suporta redes sociais, portanto não tem configurado as meta tags Facebook Open Graph Protocol e Twitter Cards.

