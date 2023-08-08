# Engineering Catalog

## A Script for a Modern Budgeting 

If you've ever worked with budgeting, answer me: how many times have you spent your precious time preparing budget estimates for your services for a client, for example? How many hours have you wasted writing and sending emails to a client, explaining about such estimates? If you answered "many times" to both questions, this project can assist you. Taking this issue into consideration, this script was created to help engineering companies modernize their service budgeting processes.

## Step 1: Clients input data
Informations like "name", "email" and "telephone number" are very important to take.

    nome = str(input('Digite seu nome: '))
    gmail = str(input('Digite o seu email: '))
    telefone = str(input('Digite seu número de telefone: '))

## Step 2: Showing the catalog until the client choose "No"
This loop component shows a catalog with a lot of services availables. The client can choose the service and the quantity of it. In the end of it, it will appear the message "Continue (Y/N)?" and if the client press "Y" he can choose another service. But if he press "N" the budge ends.

    while Pedido != 'N' and Pedido != 'n':
    wrd = 'JP Engenharia'
    tracos(wrd)
    X = int(input('Escolha o seu serviço:\n1.Projetos\n2.Consultorias\n3.Ensaios Laboratoriais\n4.Cursos\n5.Atendimento ao Cliente\nDigite o número correspondente: '))
    print('\n')
    
    if X == 1:
        wrd = 'As opções de projetos disponíveis são: '
        tracos(wrd)
        Projetos = ['Estrutural','Arquitetônico','Hidrossanitário','Elétrico','Combate a Incêndio','Acessibilidade']
        PrecosP = [3000,2000,1500,1000,800,500]

        for i in range(1,7):
            projeto = f"{i}.{Projetos[i-1]}".ljust(40)
            precop = f"R$ {PrecosP[i-1]:.2f}"
            print(f"{projeto} {precop}")
        
        print('\n')
        P = int(input('Digite o número correspondente: '))

        if P != 7:
            Qtdp = int(input(f"Você adicionou {Projetos[P-1]} no valor de R$ {PrecosP[P-1]:.2f} a unidade. Quantas unidades deseja? "))
            Comanda_Projeto = PrecosP[P-1] * Qtdp
            Cliente.append(Comanda_Projeto)
            Produtos.append(Projetos[P-1])
            Valor.append(PrecosP[P-1])
            Cont = Cont + 1
        
        Pedido = str(input('Deseja continuar o pedido (S/N)? '))
        
    if X ==  2:
        wrd = 'As opções de consultorias disponíveis são: '
        tracos(wrd)
        Consultoria = ['Viabilidade de Projetos','Riscos e Segurança','Eficiência Energética','Responsabilidade Ambiental','Normas e Regulamentações Técnicas']
        PrecosC = [1000,800,750,500,300]

        for i in range(1,6):
            consultoria = f"{i}.{Consultoria[i-1]}".ljust(40)
            precoc = f"R$ {PrecosC[i-1]:.2f}"
            print(f"{consultoria} {precoc}")
        
        print('\n')
        C = int(input('Digite o número correspondente: '))

        if C != 6:
            Qtdc = int(input(f'Você adicionou {Consultoria[C-1]} no valor de R$ {PrecosC[C-1]:.2f} a unidade. Quantas unidades deseja? '))
            Comanda_Consultoria = PrecosC[C-1] * Qtdc
            Cliente.append(Comanda_Consultoria)
            Produtos.append(Consultoria[C-1])
            Valor.append(PrecosC[C-1])
            Cont = Cont + 1
    
        Pedido = str(input('Deseja continuar o pedido (S/N)? '))
        
    if X ==  3:
        wrd = 'As opções de ensaios laboratoriais disponíveis são: '
        tracos(wrd)
        Laboratorio = ['Massa Específica de Agregados','Granulometria','Resistência à Compressão','Compactação Proctor','California Bearing Ratio','Limites de Atterberg']
        PrecosL = [1000,800,600,500,400,300]

        for i in range(1,7):
            laboratorio = f"{i}.{Laboratorio[i-1]}".ljust(40)
            precol = f"R$ {PrecosL[i-1]:.2f}"
            print(f"{laboratorio} {precol}")

        print('\n')
        L = int(input('Digite o número correspondente: '))

        if L != 7:
            Qtdl = int(input(f'Você adicionou {Laboratorio[L-1]} no valor de R$ {PrecosL[L-1]:.2f} a unidade. Quantas unidades deseja? '))
            Comanda_Laboratorio = PrecosL[L-1] * Qtdl
            Cliente.append(Comanda_Laboratorio)
            Produtos.append(Laboratorio[L-1])
            Valor.append(PrecosL[L-1])
            Cont = Cont + 1

        Pedido = str(input('Deseja continuar o pedido (S/N)? '))
        
    if X ==  4:
        wrd = 'As opções de porções cursos disponíveis são: '
        tracos(wrd)
        Cursos = ['Cálculo Estrutural','Estabilidade de Taludes','Python para Engenheiros','Power BI para Engenheiros','Excel para Engenheiros','Civil 3D']
        PrecosK = [1500,1200,1000,850,700,500]

        for i in range(1,7):
            cursos = f"{i}.{Cursos[i-1]}".ljust(40)
            precok = f"R$ {PrecosK[i-1]:.2f}"
            print(f"{cursos} {precok}")

        print('\n')
        K = int(input('Digite o número correspondente: '))

        if K != 7:
            Qtdk = int(input(f"Você adicionou {Cursos[K-1]} no valor de R$ {PrecosK[K-1]:.2f} a unidade. Quantas unidades deseja? "))
            Comanda_Cursos = PrecosK[K-1] * Qtdk
            Cliente.append(Comanda_Cursos)
            Produtos.append(Cursos[K-1])
            Valor.append(PrecosK[K-1])
            Cont = Cont + 1
       
        Pedido = str(input('Deseja continuar o pedido (S/N)? '))
     
    if X ==  5:
        print('Você acionou o serviço de atendimento ao cliente. Relate-nos o seu problema e retornaremos o seu e-mail o mais breve possível.')
        reclame = str(input('''Digite sua reclamação: '''))
        
        def reclame_email():
            corpo_email = f""" 
            <p>Cliente: {nome}\n</p>
            <p>Telefone para contato: {telefone}\n</p>
            <p>E-mail para contato: {gmail}\n\n\n</p>
            <p>Reclamação: {reclame}\n\n\n</p>
            <p>Att,\n\n</p>
            <p>A direção.</p>               
            """
            msg = email.Message()
            msg["Subject"] = f"Reclamação - Cliente {nome}"
            msg["From"] = "joaopp.eng@gmail.com"
            msg["To"] = "RH.JPEngenharia@gmail.com"
            password = "******************"
            msg.add_header('Content-type', 'text/html')
            msg.set_payload(corpo_email)
            
            s = smtp.SMTP('smtp.gmail.com', 587)
            s.starttls()
            s.login(msg["From"], password)
            s.sendmail(msg["From"], msg["To"], msg.as_string().encode('utf-8'))

        reclame_email()    
        print('Desculpe-nos o inconveniente. Sua reclamação foi enviada para o setor responsável.')

## Step 3: Calculating the total budget

    Soma = 0
    for i in range(0,Cont-1):
      Soma = Soma + Cliente[i]

## Step 4: Showing the invoice
Asking if the client wants his CPF in the budget:

    CPF = str(input('CPF (S/N)? '))
    if CPF == 'S' or CPF == 's':
        N = str(input('Digite o seu CPF: '))
        wrd = 'CUPOM FISCAL'
        tracos(wrd)
        print(f'\nCPF do cliente: {N}\n')
        p = f"{'PRODUTOS'}".ljust(40)
        v = f"{'PREÇO'}"
        wrd = f"{p} {v}"
        tracos(wrd)
    
        for i in range(1,Cont):
            produtos = f"{i}.{Produtos[i-1]}".ljust(40)
            valor = f"R$ {Valor[i-1]:.2f}"
            print(f"{produtos} {valor}")
        
        print('\n')
        t = f"{'TOTAL'}".ljust(40)
        s = float(f"{Soma}")
        wrd = f'{t} R$ {s:.2f}'
        tracos(wrd)
     
    else:
        wrd = 'CUPOM FISCAL'
        tracos(wrd)
        p = f"{'PRODUTOS'}".ljust(40)
        v = f"{'PREÇO'}"
        wrd = f"{p} {v}"
        tracos(wrd)
        
        for i in range(1,Cont):
            produtos = f"{i}.{Produtos[i-1]}".ljust(40)
            valor = f"R$ {Valor[i-1]:.2f}"
            print(f"{produtos} {valor}")
        
        print(f'TOTAL  R$ {Soma:.2f}'.ljust(40))

## Step 5: Setting up the email for automatic sending

    def enviar_email():
    corpo_email = f""" 
    <p>Olá, {nome}!</p>
    <p>Obrigado por contar com a gente. O valor do seu orçamento foi de R$ {Soma:.2f}.</p>
    <p>Para mais informações, contate-nos em nosso whatsapp:</p>
    <p>67 99197-8181</p>
    <p>Volte sempre!</p>
    """
    msg = email.Message()
    msg["Subject"] = "Orçamento - JP Engenharia"
    msg["From"] = "joaopp.eng@gmail.com"
    msg["To"] = f"{gmail}" 
    password = "*************"
    msg.add_header('Content-type', 'text/html')
    msg.set_payload(corpo_email)
    
    s = smtp.SMTP('smtp.gmail.com', 587)
    s.starttls()
    s.login(msg["From"], password)
    s.sendmail(msg["From"], msg["To"], msg.as_string().encode('utf-8'))
    print('\n')
    print('Obrigado pela confiança. Um resumo do seu orçamento foi enviado em seu e-mail.')
    
## Step g: Sending the email

    enviar_email()


      
