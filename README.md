# Comandos-Laravel
Alguns comandos e métodos do laravel

COMANDOS DE CRIAÇÃO (MAKE)

-COMANDO PARA CRIAR MODEL , MIGRATION, FACTORY E CONTROLLER NO ESTILO RESOURCE DE UMA SÓ VEZ
  php artisan make:model Models\Category -m -f -r   (Utilizar o padrão sempre no singular)

-COMANDO PARA GERAR SÓ MODEL
  php artisan make:model Models\Category

-COMANDO PARA GERAR SÓ A FACTORY
  php artisan make:factory --model=Models\Category CategoryFactory  (PRIMEIRO PASSA O NOME DO MODEL E DPS O NOME DA FACTORY)

-COMANDO PARA CRIAR MIGRATION
  php artisan make:migration create_categories_table --create=categories

-COMANDO PARA CRIAR CONTROLLER LIGADO A UM CERTO MODEL
  php artisan make:controller --model=Models\Category --resource CategoryController

-COMANDO PARA CRIAR SEEDER
  php artisan make:seeder CategoriesTableSeeder  (PADRÃO SEEDER PLURAL)

-COMANDO PARA RODAR UMA SEED
  php artisan db:seed

-COMANDO PARA RODAR MIGRATE E SEEDER
  php artisan migrate:refresh --seed

-COMANDO PARA CRIAR UM FORM REQUEST(ESTRUTURA PARA VALIDAÇÃO DE DADOS ENVIADOS NA REQUEST)
  php artisan make:request CategoryRequest

- COMANDO PARA CRIAR UMA TABLE PIVOT (RELACIONAMENTO MUITOS PARA MUITOS) NO LARAVEL
  php artisan make:migration create_category_product_table --create   (TEM QUE SER O NOME DADOS DUAS TABELA, NO SINGULAR, A PRIMEIRA     TABELA VAI POR ORDEM ALFABETICA)
  
  
  --------------------------------------------------------------------------------------------------------------------------------------
  
  MÉTODOS
  
  - MÉTODO fill();
  O MÉTODO fill() RECEBE UM ARRAY COM AS INFORMAÇÕES QUE A GENTE QUER ATUALIZAR

- MÉTODO ATTACH();
  Usado na hora que queremos criar um novo registro com relacionamento já existente, ex:
    $category->products()->attach(2);

- MÉTODO DETACH();
  Usado para remover o relacionamento (na tabela pivot), ex:
    $product->categories()->detach([3, 5]);
