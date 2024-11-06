import os
os.system('cls')

registros = []


def adicionar_registro():
    tipo = input("Tipo (Treino ou Competição): ")
    data = input("Data (DD/MM/AAAA): ")
    distancia = float(input("Distância percorrida (em km): "))
    tempo = float(input("Tempo (em minutos): "))
    localizacao = input("Localização: ")
    condicoes_climaticas = input("Condições Climáticas: ")
    
    registro = {
        "tipo": tipo,
        "data": data,
        "distancia": distancia,
        "tempo": tempo,
        "localizacao": localizacao,
        "condicoes_climaticas": condicoes_climaticas
    }
    registros.append(registro)
    print("Registro adicionado com sucesso!")

def visualizar_registros():
    if not registros:
        print("Nenhum registro encontrado.")
        return
    for i, registro in enumerate(registros, start=1):
        print(f"\nRegistro {i}:")
        for chave, valor in registro.items():
            print(f"{chave.capitalize()}: {valor}")
    print("\n")

def atualizar_registro():
    visualizar_registros()
    indice = int(input("Número do registro para atualizar: ")) - 1
    if 0 <= indice < len(registros):
        registros[indice]["data"] = input("Nova Data (DD/MM/AAAA): ")
        registros[indice]["distancia"] = float(input("Nova Distância (em km): "))
        registros[indice]["tempo"] = float(input("Novo Tempo (em minutos): "))
        registros[indice]["localizacao"] = input("Nova Localização: ")
        registros[indice]["condicoes_climaticas"] = input("Novas Condições Climáticas: ")
        print("Registro atualizado com sucesso!")
    else:
        print("Registro inválido.")

def excluir_registro():
    visualizar_registros()
    indice = int(input("Número do registro para excluir: ")) - 1
    if 0 <= indice < len(registros):
        registros.pop(indice)
        print("Registro excluído com sucesso!")
    else:
        print("Registro inválido.")

def filtrar_registros():
    criterio = input("Filtrar por Distância ou Tempo? ").lower()
    valor = float(input("Valor para filtrar (em km ou minutos): "))
    
    filtrados = []
    for registro in registros:
        if (criterio == "distancia" and registro["distancia"] == valor) or \
           (criterio == "tempo" and registro["tempo"] == valor):
            filtrados.append(registro)
    
    if filtrados:
        for i, registro in enumerate(filtrados, start=1):
            print(f"\nRegistro Filtrado {i}:")
            for chave, valor in registro.items():
                print(f"{chave.capitalize()}: {valor}")
    else:
        print("Nenhum registro encontrado com esse critério.")

def definir_meta():
    meta = input("Defina uma meta (ex.: 'Correr 100 km este mês'): ")
    print(f"Meta definida: {meta}")
    print("Acompanhe o progresso nos registros.")

def sugerir_treino():
    if registros:
        import random
        sugestao = random.choice(registros)
        print("Sugestão de treino:")
        for chave, valor in sugestao.items():
            print(f"{chave.capitalize()}: {valor}")
    else:
        print("Nenhum treino registrado para sugerir.")

def estatisticas():
    total_distancia = sum([registro["distancia"] for registro in registros])
    total_tempo = sum([registro["tempo"] for registro in registros])
    print(f"\nEstatísticas:")
    print(f"Total de distância percorrida: {total_distancia} km")
    print(f"Total de tempo em treinos: {total_tempo} minutos")
    if len(registros) > 0:
        print(f"Distância média por treino: {total_distancia / len(registros):.2f} km")
        print(f"Tempo médio por treino: {total_tempo / len(registros):.2f} minutos")
    else:
        print("Nenhum treino registrado para cálculo de estatísticas.")

def menu():
    while True:
        print("=== Gerenciamento de Treinos de Corrida ===")
        print("1. Adicionar Treino ou Competição")
        print("2. Visualizar Registros")
        print("3. Atualizar Registro")
        print("4. Excluir Registro")
        print("5. Filtrar Registros")
        print("6. Definir Meta")
        print("7. Sugerir Treino")
        print("8. Estatísticas")
        print("9. Sair")
        
        escolha = input("Escolha uma opção: ")
        
        if escolha == "1":
            adicionar_registro()
        elif escolha == "2":
            visualizar_registros()
        elif escolha == "3":
            atualizar_registro()
        elif escolha == "4":
            excluir_registro()
        elif escolha == "5":
            filtrar_registros()
        elif escolha == "6":
            definir_meta()
        elif escolha == "7":
            sugerir_treino()
        elif escolha == "8":
            estatisticas()
        elif escolha == "9":
            print("Saindo do sistema...")
            break
        else:
            print("Opção inválida. Tente novamente.")
        
        input("\nPressione Enter para continuar...")

menu()