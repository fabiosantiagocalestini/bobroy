import pymysql
conexao = pymysql.connect(
    host = 'localhost',
    user = 'root',
    passwd = '',
    database = 'pneus'
)
cursor = conexao.cursor()

def din():
    print('''            \033[4;32mPAGAMENTO\033[m
    [1] A VISTA (DINHEIRO/ CARTÃO)
    [2] PARCELADO NO CARTÃO DE CRÉDITO''')
    pagamento = int(input('QUAL É A FORMA DE PAGAMENTO?: '))
    if pagamento == 1:
        print('PAGAMENTO A VISTA TEM DESCONTO DE 10%')
        desconto = totpneu - (totpneu * 10 / 100)
        print(f'\033[4mOS PNEUS QUE CUSTAVAM R${totpneu:.2f}, COM DESCONTO DE 10% PASSARAM A CUSTAR R${desconto:.2f}\033[m')
    elif pagamento == 2:
        print('PARCELAMOS EM ATÉ 12 VEZES COM JUROS DE 5%')
        parcelas = int(input('EM QUANTAS PARCELAS O VALOR SERÁ DIVIDIDO?: '))
        novopreço = totpneu / parcelas
        juros = (novopreço * 5 / 100) * 10
        preçofinal = totpneu + novopreço
        preçopneu = preçofinal / parcelas
        print(f'\033[4mO VALOR DE R${totpneu:.2f} TERÁ JUROS DE 5% E SERÁ DIVIDIDO EM {parcelas} VEZES DE R${preçopneu:.2f}')
        print(f'O PREÇO DOS PNEUS FICOU EM R${preçofinal:.2f}\033[m')


print('-='*20)
print('\033[1;31mBEM VINDO A BORRACHARIA DO BOB ROY 2.0\033[m')
print('-='*20)
opção = 0
while opção != 6:
    print('''    [1] CONSERTO SIMPLES
    [2] CONSERTO INTERNO FRIO
    [3] VULCANIZAÇÃO
    [4] MONTAGEM/DESMONTAGEM DE PNEUS
    [5] PNEUS NOVOS
    [6] SAIR DO PROGRAMA''')
    print('-='*20)
    opção = int(input('>>>\033[35mQUAL É A SUA OPÇÃO?\033[m<<<: '))
    if opção == 1:
        print('CONSERTO: R$20.00')
        consertosimples = 20.00
        serviço1 = int(input('QUANTOS CONSERTOS DESEJA FAZER?: '))
        total = consertosimples * serviço1
        print(f'OS {serviço1} CONSERTOS FICARAM EM R${total:.2f}')
    elif opção == 2:
        print('CONSERTO INTERNO FRIO: R$40.00')
        consertofrio = 40.00
        serviço2 = int(input('QUANTOS CONSERTOS DESEJA FAZER?: '))
        total = consertofrio * serviço2
        print(f'OS {serviço2} CONSERTOS FICARAM EM R${total:.2f} ')
    elif opção == 3:
        print('VULCANIZAÇÃO: R$70.00')
        vulcanização = 70.00
        serviço3 = int(input('QUANTOS PNEUS PRECISA VULCANIZAR?: '))
        total = vulcanização * serviço3
        print(f'AS {serviço3} VULCANIZAÇÕES FICARAM EM R${total:.2f}')
    elif opção == 4:
        print('MONTAGEM/DESMONTAGEM DE PNEUS: R$25.00')
        montagem = 25.00
        serviço4 = int(input('QUANTOS PNEUS SERÃO MONTADOS?: '))
        total = montagem * serviço4
        print(f'OS {serviço4} MONTAGENS FICARAM EM R${total:.2f}')
    elif opção == 5:
        print('TRABALHAMOS COM PNEUS DO ARO 13 ATÉ O ARO 30')
        print(f'             \033[4;34mTOYO/YOKOHAMA\033[m      ')
        aro = int(input('SEU CARRO USA PNEUS DE QUAL ARO?: '))
        if aro == 13:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 13":^52}')
            print('-'*45)
            print('''           [1]  145/80/13..........R$119.00
           [2]  155/80/13..........R$119.OO
           [3]  165/65/13..........R$189.00
           [4]  165/70/13..........R$139.00
           [5]  165/80/13..........R$179.00
           [6]  175/65/13..........R$189.00
           [7]  175/70/13..........R$149.00
           [8]  175/80/13..........R$199.00
           [9}  185/70/13..........R$199.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 14:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 14":^52}')
            print('-'*45)
            print('''           [1]  175/65/14..........R$219.00
           [2]  175/70/14..........R$229.00
           [3]  175/80/14..........R$380.00
           [4]  185/60/14..........R$219.00
           [5]  185/65/14..........R$239.00
           [6]  185/70/14..........R$299.00
           [7]  185/R/14...........R$419.00
           [8]  195/60/14..........R$259.00
           [9]  195/65/14..........R$269.00
           [10] 195/70/14..........R$319.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(F'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 15:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 15":^52}')
            print('-'*45)
            print('''            [1]  175/65/15..........R$299.00
            [2]  185/55/15..........R$319.00
            [3]  185/60/15..........R$329.00
            [4]  185/65/15..........R$339.00
            [5]  195/45/15..........R$379.00
            [6]  195/50/15..........R$339.00
            [7]  195/55/15..........R$349.00
            [8]  195/60/15..........R$359.00
            [9]  195/65/15..........R$369.00
            [10] 195/70/15..........R$429.00
            [11] 205/60/15..........R$389.00
            [12] 205/65/15..........R$450.00
            [13] 205/70/15..........R$469.00
            [14] 225/75/15..........R$519.00
            [15] 235/75/15..........R$539.00
            [16] 255/60/15..........R$619.00
            [17] 255/70/15..........R$559.00
            [18] 255/75/15..........R$569.00
            [19] 265/70/15..........R$579.00
            [20] 265/75/15..........R$599.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 16:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 16":^52}')
            print('-'*45)
            print('''            [1]  185/55/16..........R$349.00
            [2]  195/45/16..........R$359.00
            [3]  195/50/16..........R$349.00
            [4]  195/55/16..........R$369.00
            [5]  195/60/16..........R$419.00
            [6]  205/45/16..........R$369.00
            [7]  205/50/16..........R$379.00
            [8]  205/55/16..........R$349.00
            [9]  205/60/16..........R$389.00
            [10] 205/75/16..........R$499.00
            [11] 215/55/16..........R$389.00
            [12] 215/60/16..........R$389.00
            [13] 215/65/16..........R$429.00
            [14] 215/75/16..........R$529.00
            [15] 225/50/16..........R$459.00
            [16] 225/55/16..........R$459.00
            [17] 225/65/16..........R$429.00
            [18] 225/70/16..........R$529.00
            [19] 225/75/16..........R$549.00
            [20] 235/60/16..........R$499.00
            [21] 235/70/16..........R$539.00
            [22] 245/70/16..........R$569.00
            [23] 245/75/16..........R$579.00
            [24] 255/70/16..........R$599.00
            [25] 255/75/16..........R$609.00
            [26] 265/70/16..........R$629.00
            [27] 265/75/16..........R$649.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 17:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 17":^52}')
            print('-'*45)
            print('''            [1]  165/40/17..........R$389.00
            [2]  185/35/17..........R$399.00
            [3]  195/40/17..........R$319.00
            [4]  195/45/17..........R$329.00
            [5]  205/40/17..........R$329.00
            [6]  205/45/17..........R$339.00
            [7]  205/50/17..........R$399.00
            [8]  205/55/17..........R$419.00
            [9]  215/45/17..........R$389.00
            [10] 215/50/17..........R$399.00
            [11] 215/55/17..........R$439.00
            [12] 225/45/17..........R$399.00
            [13] 225/65/17..........R$489.00
            [14] 225/50/17..........R$459.00
            [15] 235/55/17..........R$479.00
            [16] 235/60/17..........R$499.00
            [17] 255/65/17..........R$529.00
            [18] 265/65/17..........R$629.00
            [19] 265/70/17..........R$699.00
            [20] 315/75/17..........R$1399.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 18:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 18":^52}')
            print('-'*45)
            print('''            [1]  165/40/18..........R$399.00
            [2]  205/35/18..........R$409.00
            [3]  205/45/18..........R$429.00
            [4]  215/35/18..........R$429.00
            [5]  215/40/18..........R$449.00
            [6]  215/45/18..........R$449.00
            [7]  225/45/18..........R$459.00
            [8]  225/50/18..........R$469.00
            [9]  225/55/18..........R$479.00
            [10] 235/40/18..........R$479.00
            [11] 235/45/18..........R$489.00
            [12] 235/50/18..........R$489.00
            [13] 235/55/18..........R$489.00
            [14] 235/60/18..........R$499.00
            [15] 245/45/18..........R$479.00
            [16] 245/60/18..........R$519.00
            [17] 255/55/18..........R$549.00
            [18] 255/60/18..........R$599.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 19:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 19":^52}')
            print('-'*45)
            print('''            [1]  225/35/19..........R$429.00
            [2]  225/55/19..........R$529.00
            [3]  235/35/19..........R$459.00
            [4]  235/55/19..........R$539.00
            [5]  245/35/19..........R$479.00
            [6]  255/35/19..........R$499.00
            [7]  255/50/19..........R$529.00
            [8]  255/55/19..........R$559.00
            [9]  275/35/19..........R$619.00''')
            print('-'*45)
            pneunovo = int(input('QUAL PNEU VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 20:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 20":^52}')
            print('-'*45)
            print('''            [1]  225/30/20..........R$499.00
            [2]  225/35/20..........R$499.00
            [3]  235/30/20..........R$509.00
            [4]  235/35/20..........R$509.00
            [5]  245/45/20..........R$529.00
            [6]  245/50/20..........R$579.00
            [7]  265/50/20..........R$699.00
            [8]  275/40/20..........R$749.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 21:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 21":^52}')
            print('-'*45)
            print('''            [1]  265/40/21..........R$799.00
            [2]  275/40/21..........R$849.00
            [3]  295/35/21..........R$1199.00
            [4]  295/40/21..........R$1299.00
            [5]  305/35/21..........R$1399.00
            [6]  315/40/21..........R$1499.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 22:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 22":^52}')
            print('-'*45)
            print('''            [1]  245/30/22..........R$699.00
            [2]  265/35/22..........R$799.00
            [3]  285/35/22..........R$829.00
            [4]  285/40/22..........R$859.00
            [5]  295/30/22..........R$959.00
            [6]  295/35/22..........R$999.00
            [7]  305/40/22..........R$1099.00
            [8]  305/45/22..........R$1199.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f} ')
            din()
        elif aro == 24:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 24":^52}')
            print('-'*45)
            print('''            [1]  245/30/24..........R$699.00
            [2]  255/35/24..........R$799.00
            [3]  275/40/24..........R$899.00
            [4]  285/45/24..........R$999.00
            [5]  295/35/24..........R$1099.00
            [6]  305/35/24..........R$1199.00
            [7]  305/40/24..........R$1299.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 26:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 26":^52}')
            print('-'*45)
            print('''            [1]  275/35/26..........R$999.00
            [2]  285/40/26..........R$1499.00
            [3]  295/40/26..........R$1599.00
            [4]  305/35/26..........R$1699.00
            [5]  315/40/26..........R$1899.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 28:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 28":^52}')
            print('-'*45)
            print('''            [1]  275/40/28..........R$1599.00
            [2]  285/40/28..........R$1799.00
            [3]  295/35/28..........R$1899.00
            [4]  295/40/28..........R$1999.00
            [5]  295/45/28..........R$2199.00
            [6]  305/40/28..........R$2399.00
            [7]  315/40/28..........R$2399.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        elif aro == 30:
            print('-'*45)
            print(f'{"TABELA DE PREÇO PNEUS ARO 30":^52}')
            print('-'*45)
            print('''            [1]  295/35/30..........R$1999.00
            [2]  305/35/30..........R$2299.00
            [3]  305/40/30..........R$2399.00
            [4]  315/30/30..........R$2499.00
            [5]  325/25/30..........R$2999.00''')
            print('-'*45)
            pneunovo = int(input('QUAL É O PNEU QUE VOCÊ UTILIZA?: '))
            quant = int(input('QUANTOS PNEUS DESEJA COMPRAR?: '))
            preço = float(input('PREÇO DO PNEU ADQUIRIDO: '))
            totpneu = quant * preço
            print(f'OS {quant} PNEUS ARO {aro} FICARAM EM R${totpneu:.2f}')
            din()
        else:
            print('OPÇÃO INVALIDA...REINICIANDO O PROGRAMA')
    elif opção == 6:
        while True:
            resp = str(input('DESEJA SAIR DO PROGRAMA? [S/N]: '))
            if resp in 'Ss':
                break
            if resp in 'Nn':
                opção = int(input('>>>\033[35mQUAL É A SUA OPÇÃO?\033[m<<<: '))
    else:
        print(f'OPÇÃO INVALIDA...TENTE NOVAMENTE')
print('         \033[1;36mFIM DO PROGRAMA!')
print('\033[1;36mMUITO OBRIGADO PELA PREFERÊNCIA E VOLTE SEMPRE!\033[m')
