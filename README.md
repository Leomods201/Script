# Simulando bases como listas
base_principal = ["itemA", "itemB", "itemC"]
sua_base = []

def mostrar_bases():
    print("\nItens na base principal:")
    for idx, item in enumerate(base_principal, 1):
        print(f"{idx}. {item}")
    print("\nItens na sua base:")
    for idx, item in enumerate(sua_base, 1):
        print(f"{idx}. {item}")

def teleportar_item():
    mostrar_bases()
    if not base_principal:
        print("A base principal está vazia.")
        return
    escolha = input("\nDigite o número do item que deseja teletransportar para sua base: ")
    try:
        idx = int(escolha) - 1
        if 0 <= idx < len(base_principal):
            item = base_principal.pop(idx)
            sua_base.append(item)
            print(f"Item '{item}' teletransportado para sua base!")
        else:
            print("Escolha inválida.")
    except ValueError:
        print("Entrada inválida.")

def menu():
    while True:
        print("\n=== MENU TELETRANSPORTE ===")
        print("1. Ver bases")
        print("2. Teletransportar item para sua base")
        print("3. Sair")
        escolha = input("Escolha uma opção: ")

        if escolha == "1":
            mostrar_bases()
        elif escolha == "2":
            teleportar_item()
        elif escolha == "3":
            print("Saindo...")
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    menu()
