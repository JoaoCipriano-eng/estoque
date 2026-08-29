# Projeto de estoque de dados 


    registro de novos produtos
    if opcao == "0":
        print("==== Registro do produto =====")
        registro = input("Digite o nome do produto: ")
        quantidade_prouto = int(input("Digite o quantidade de produto: "))
        valor_prouto = float(input("Digite o valor do produto: "))

        novo_produto ={
              "nome": registro,
              "quantidade": quantidade_prouto,
              "valor": valor_prouto }

        estoque.append(novo_produto)

        #Estoque
    elif opcao == "1":
        print("===== Estoque =====")
        for produto in estoque:
            print(f"produto: {produto["nome"]} | "
                  f"Quantidade: {produto['quantidade']} |"
                  f"preço:{produto['valor']:.2f} |")

    #Registo dos produtos
    elif opcao == "2":
        print("==== Registro ====")
        nome_produto = input("Digite o nome do produto: ")
        # coventendo input de quantidade para inteiro
        quantidade_prouto = int(input("Digite o quantidade de produto: "))

        produto_encontrado = False
        for produto in estoque:
            if produto["nome"] == nome_produto:
                produto["quantidade"] += quantidade_prouto
                produto_encontrado = True
                print("==== Registro com sucesso ====")

        if not produto_encontrado:
            print("==== produto nao encontrado =====")


        # Saido de produto
    elif opcao == "3":
        saida_produto = input("Digite o nome do produto: ")
        quantidade_saido = int(input("quantidade de saida do produto: "))
        produto_encontrado = False

        for produto in estoque:
            if produto["nome"] == saida_produto:
                produto_encontrado = True

                if produto["quantidade"] >= quantidade_saido:
                    produto["quantidade"] -= quantidade_saido
                    print("==== sainda registrado =====")
                else:
                    print("==== sem estoque =====")
        if not produto_encontrado:
          print("==== produto nao encontrado =====")
        #saida
        elif opcao == "4":
         print("===== FIM DO SISTEMA =====")
         break

    else:
     print("Opção inválida. Escolha uma opção entre 0 e 4.")
