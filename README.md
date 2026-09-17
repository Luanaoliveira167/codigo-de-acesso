# codigo-de-acesso
codigo sistema do site fimdefila
from services.agendamento import Agendamento
from services.fila_service import FilaService


def menu():
    print("\n===== FILASAÚDE =====")
    print("1 - Cadastrar paciente")
    print("2 - Consultar vagas")
    print("3 - Agendar consulta")
    print("4 - Cancelar consulta")
    print("5 - Entrar na fila de espera")
    print("6 - Consultar posição na fila")
    print("7 - Confirmar consulta")
    print("8 - Painel do gestor")
    print("9 - Relatórios")
    print("0 - Sair")


def main():
    agendamento = Agendamento()
    fila = FilaService()

    while True:
        menu()
        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            agendamento.cadastrar_paciente()

        elif opcao == "2":
            agendamento.consultar_vagas()

        elif opcao == "3":
            agendamento.agendar_consulta()

        elif opcao == "4":
            agendamento.cancelar_consulta()

        elif opcao == "5":
            fila.adicionar_paciente()

        elif opcao == "6":
            fila.consultar_posicao()

        elif opcao == "7":
            agendamento.confirmar_consulta()

        elif opcao == "8":
            agendamento.painel_gestor()

        elif opcao == "9":
            agendamento.gerar_relatorio()

        elif opcao == "0":
            print("Sistema encerrado.")
            break

        else:
            print("Opção inválida!")


if __name__ == "__main__":
    main()
