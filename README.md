# Test-Practic-Dev-TGR
Resolução da atividade prática para a TGR

# Produtos App

Este projeto é um sistema de CRUD de produtos.

## Pré-requisitos

- Laravel 8 ou superior
- MySQL ou outro banco de dados de sua escolha

## Configuração do Banco de Dados

1. No arquivo `.env`, configure as credenciais de banco de dados:

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=produtos_app
DB_USERNAME=root
DB_PASSWORD=



2. Para criar as tabelas no banco de dados, execute o comando:

```bash
php artisan migrate

Se precisar de dados de exemplo para popular o banco, crie um seeder ou forneça um arquivo SQL com os dados iniciais.

### **3. (Opcional) Seeder ou Arquivo SQL para Dados Iniciais**
Se for necessário incluir alguns dados iniciais no banco de dados (como alguns produtos), você pode criar um **seeder** no Laravel ou até mesmo fornecer um arquivo SQL com os dados.

#### **Criando um Seeder no Laravel**:
Para criar um seeder que preenche o banco com produtos de exemplo, você pode usar o seguinte comando:

```bash
php artisan make:seeder ProdutoSeeder


Isso criará o arquivo ProdutoSeeder.php em database/seeders. Dentro desse arquivo, você pode adicionar alguns dados fictícios:
use App\Models\Produto;
use Illuminate\Database\Seeder;

class ProdutoSeeder extends Seeder
{
    public function run()
    {
        Produto::create([
            'nome' => 'Produto 1',
            'descricao' => 'Descrição do Produto 1',
            'preco' => 10.00,
            'quantidade' => 100,
        ]);

        Produto::create([
            'nome' => 'Produto 2',
            'descricao' => 'Descrição do Produto 2',
            'preco' => 20.00,
            'quantidade' => 200,
        ]);
    }
}


Depois, no terminal, você pode rodar o comando para popular o banco de dados com os dados fictícios:
php artisan db:seed --class=ProdutoSeeder


Aqui estão os comandos para rodar no ambiente de desenvolvimento, uma vez que o projeto for baixado:
# Instalar dependências
composer install

# Configurar o .env
cp .env.example .env

# Gerar chave de aplicação
php artisan key:generate

# Rodar as migrations
php artisan migrate

# Rodar os seeders (se necessário)
php artisan db:seed

# Iniciar o servidor local
php artisan serve

