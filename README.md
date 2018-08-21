/* Autor: Idelvando Cerqueira de Souza
Componente Curricular: MI - Algoritmos
Concluido em: 02/05/2018
Declaro que este código foi elaborado por mim de forma individual e não contém nenhum trecho de código de outro colega ou de outro autor,
tais como provindos de livros e apostilas, e páginas ou documentos eletrônicos da Internet.
Qualquer trecho de código de outra autoria que não a minha está destacado com uma citação para o autor e a fonte do código,
e estou ciente que estes trechos não serão considerados para fins de avaliação.*/
/*A ideia deste projeto é desenvolver um programa básico apresentando somente os mecanismos fundamentais da linguagem C, sem se preocupar com modularização ou estruturas de dados mais avançadas, o intuito é introduzir o estudante à linguagem C.*/

include <stdlib.h>
include <stdio.h>
include <locale.h>

int main ()
{
  setlocale(LC_ALL, "Portuguese");
  int OpcaoMenu=0, ContadorEleitores=0, Presidente=0, Governador=0, Senador=0, DepFederal=0, DepEstadual=0, Confirma=0; //Variáveis utilizadas para guardar os votos em cada categoria;
  int Maeli=0, AnBrasil=0, Lissandro=0, MaiaDaAna=0, Gentil=0, DonaSelma=0, Gutemberg=0, Fernando=0, AnaVitoria=0, PauloGui=0; //Variáveis utilizadas para guardar os votos de cada candidato;
  int AnaRita=0, AnaGui=0, Adalberto=0, BrancosDepEstad=0, NulosDepEstad=0, BrancosDepFed=0, NulosDepFed=0, BrancosSenad=0; //Variáveis utilizadas para guardar os votos em cada categoria;
  int NulosSenad=0, BrancosGov=0, NulosGov=0, BrancosPresid=0, NulosPresid=0; //Variáveis utilizadas para guardar os votos nulos e brancos em cada categoria;
  int ValidosDepEstad=0, ValidosDepFed=0, ValidosSenador=0, ValidosGov=0, ValidosPresid=0; //Variáveis utilizadas para guardar os votos válidos em cada categoria;
  int Feminino=0, Masculino=0, ContMascFem=0;
  float PercentMasculino=0, PercentFeminino=0;
  float PorcentAnaRita=0, PorcentAnaGui=0, PorcentAdalberto=0, PorcentAnaVitoria=0, PorcentPauloGui=0; //Variáveis utilizadas para calcular o percentual de botos em cada candidato;
  float PorcentFernando=0, PorcentMaiaDaAna=0, PorcentGentil=0, PorcentDonaSelma=0; //Variáveis utilizadas para calcular o percentual de botos em cada candidato;
  float PorcentLissandro=0, PorcentMaeli=0, PorcentAnBrasil=0, PorcentGutemberg=0; //Variáveis utilizadas para calcular o percentual de botos em cada candidato;
  float PorcentBrancosDepEst=0, PorcentBrancosDepFed=0, PorcentBrancosSenad=0, PorcentBrancosGov=0, PorcentBrancosPresid=0; //Variáveis utilizadas para calcular o percentual de botos em cada categoria;
  float PorcentNulosDepEst=0, PorcentNulosDepFed=0, PorcentNulosSenad=0, PorcentNulosGov=0, PorcentNulosPresid=0; //Variáveis utilizadas para calcular o percentual de botos em cada categoria;
  double TituloEleitoral=0; //Variável utilizada para guardar o título de cada eleitor;

  do
  {
    /*
    Menu inicial do programa;
    Três diferentes opções de entrada.
    */
    puts ("---------------------------------------------------------------------------------------------");
    printf ("*|ELEIÇÕES DE 2018 #VEMPRAURNA!\n");
    printf ("*|ESCOLHA UMA DAS OPÇÕES ABAIXO PARA PROSSEGUIR:\n");
    printf ("*|\t[1] - VOTAÇÃO GERAL:\n");
    printf ("*|\t[2] - GERAR RELATÓRIO FINAL ESTATÍSTICO:\n");
    printf ("*|\t[3] - PARAR EXECUÇÃO DO PROGRAMA:\n");
    printf ("*|[TSEC - TRIBUNAL SUPERIOR DE ECOMP]\n");
    printf ("---------------------------------------------------------------------------------------------\n");
    scanf ("%d", &OpcaoMenu);
    setbuf(stdin, NULL);
    system ("cls");

    switch (OpcaoMenu)
    {
    case 1:
      /*
      Saída e entrada com o título de elitor;
      Juntamente com o seu devido tratamento de erro para receber exatos 12 números.
      */
      do
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|INFORME OS NÚMEROS DO SEU TÍTULO ELEITORAL:\n");
        printf ("-------------------------------------------------------------------------------------------\n");
        scanf ("%lf", &TituloEleitoral);
        setbuf(stdin, NULL);
        system ("cls");
        if (TituloEleitoral <100000000000 || TituloEleitoral >999999999999)
        {
          puts ("---------------------------------------------------------------------------------------------");
          printf ("O CONJUNTO DE NÚMEROS INFORMADO NÃO POSSUE 12 DÍGITOS OU NÃO CORRESPONDE A NÚMEROS INTEIROS!\n");
          printf ("POR FAVOR, TENTE NOVAMENTE!\n");
          printf ("-------------------------------------------------------------------------------------------\n");
          system ("pause");
          system ("cls");
        }
      }
      while(TituloEleitoral <100000000000 || TituloEleitoral >999999999999);
      /*
      Votação dividida por categoria;
      Juntamente com seu devido tratamento de erro que funciona da seguinte forma:
      Existem as opções de votos em cada categoria, dentre elas cada eleitor pode escolher se vota em algum
      dos candidatos ou vota 1 para branco, qualquer outro número além dos apresentados nas saídas de cada categoria
      o usuário será redirecionado para uma tela com uma mensagem o avisando que o número digitado corresponde a
      nenhuma das opçoes e que seu voto será considerado como nulo. Cada categoria é composta por um do while e por
      uma condicional. Além disso, se o candidato escolher uma das opções válidas será exibida uma mensagem pedindo
      para ele confirmar o voto, como é feito em urnas convencionais.
      Linhas 76 à 265.
      */
      do
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|[CANDIDATOS AO CONGRESSO FEDERAL BRASILEIRO] [CARGO: DEPUTADO ESTADUAL DA BAHIA]\n");
        printf ("|\t*Sra. Ana Rita Pacheco (nº51)\n");
        printf ("|\t*Sra. Ana Guilherme (nº34)\n");
        printf ("|\t*Sr. Adalberto Campos (nº11)\n");
        printf ("|\t*BRANCO: (Nº1)\n");
        printf ("|INFORME O Nº DA OPÇÃO ESCOLHIDA:\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        scanf ("%d", &DepEstadual);
        setbuf(stdin, NULL);

        if (DepEstadual == 1 || DepEstadual == 51 || DepEstadual == 34 || DepEstadual == 11)
        {
          puts ("---------------------------------------------------------------------------------------------");
          printf ("|DIGITE (Nº3) PARA CONFIRMAR SEU VOTO OU QUALQUER OUTRO PARA RETORNAR À VOTAÇÃO:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
        else
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|*ATENÇÃO:\n");
          printf ("|O NÚMERO DIGITADO CORRESPONDE A NENHUMA DAS ALTERNATIVAS DE VOTAÇÃO!\n");
          printf ("|SEU VOTO SERÁ CONSIDERADO COMO NULO!\n");
          printf ("|DIGITE (Nº2) PARA CORRIGIR E REFAZER A VOTAÇÃO OU (Nº3) PARA PROSSEGUIR:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
      }
      while (Confirma != 3);

      do
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|[CANDIDATOS AO CONGRESSO FEDERAL BRASILEIRO] [CARGO: DEPUTADO FEDERAL]\n");
        printf ("|\t*Sra. Ana Vitória (nº56)\n");
        printf ("|\t*Sr. Paulo Guilherme (nº33)\n");
        printf ("|\t*BRANCO: (Nº1)\n");
        printf ("|INFORME O Nº DA OPÇÃO ESCOLHIDA:\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        scanf ("%d", &DepFederal);
        setbuf(stdin, NULL);

        if (DepFederal == 1 || DepFederal == 56 || DepFederal == 33)
        {
          puts ("---------------------------------------------------------------------------------------------");
          printf ("|DIGITE (Nº3) PARA CONFIRMAR SEU VOTO OU QUALQUER OUTRO PARA RETORNAR À VOTAÇÃO:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
        else
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|*ATENÇÃO:\n");
          printf ("|O NÚMERO DIGITADO CORRESPONDE A NENHUMA DAS ALTERNATIVAS DE VOTAÇÃO!\n");
          printf ("|SEU VOTO SERÁ CONSIDERADO COMO NULO!\n");
          printf ("|DIGITE (Nº2) PARA CORRIGIR E REFAZER A VOTAÇÃO OU (Nº3) PARA PROSSEGUIR:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
      }
      while (Confirma != 3);

      do
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|[CANDIDATOS AO SENADO BRASILEIRO] [CARGO: SENADOR]\n");
        printf ("|\t*Sr. Gutemberg Silva (nº4)\n");
        printf ("|\t*Sr. Fernando Fernandes (nº67)\n");
        printf ("|\t*BRANCO: (Nº1)\n");
        printf ("|INFORME O Nº DA OPÇÃO ESCOLHIDA:\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        scanf ("%d", &Senador);
        setbuf(stdin, NULL);

        if (Senador == 1 || Senador == 4 || Senador == 67)
        {
          puts ("---------------------------------------------------------------------------------------------");
          printf ("|DIGITE (Nº3) PARA CONFIRMAR SEU VOTO OU QUALQUER OUTRO PARA RETORNAR À VOTAÇÃO:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
        else
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|*ATENÇÃO:\n");
          printf ("|O NÚMERO DIGITADO CORRESPONDE A NENHUMA DAS ALTERNATIVAS DE VOTAÇÃO!\n");
          printf ("|SEU VOTO SERÁ CONSIDERADO COMO NULO!\n");
          printf ("|DIGITE (Nº2) PARA CORRIGIR E REFAZER A VOTAÇÃO OU (Nº3) PARA PROSSEGUIR:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
      }
      while (Confirma != 3);

      do
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|[CANDIDATOS AO GOVERNO DA BAHIA] [CARGO: GOVERNADOR]\n");
        printf ("|\t*Sr. Maia da Ana (nº38)\n");
        printf ("|\t*Sr. Gentil (nº40)\n");
        printf ("|\t*Sra. Dona Selma Silva (nº18)\n");
        printf ("|\t*BRANCO: (Nº1)\n");
        printf ("|INFORME O Nº DA OPÇÃO ESCOLHIDA:\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        scanf ("%d", &Governador);
        setbuf(stdin, NULL);

        if (Governador == 1 || Governador == 40 || Governador == 38 || Governador == 18)
        {
          puts ("---------------------------------------------------------------------------------------------");
          printf ("|DIGITE (Nº3) PARA CONFIRMAR SEU VOTO OU QUALQUER OUTRO PARA RETORNAR À VOTAÇÃO:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
        else
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|*ATENÇÃO:\n");
          printf ("|O NÚMERO DIGITADO CORRESPONDE A NENHUMA DAS ALTERNATIVAS DE VOTAÇÃO!\n");
          printf ("|SEU VOTO SERÁ CONSIDERADO COMO NULO!\n");
          printf ("|DIGITE (Nº2) PARA CORRIGIR E REFAZER A VOTAÇÃO OU (Nº3) PARA PROSSEGUIR:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
      }
      while (Confirma != 3);

      do
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|[CANDIDATOS À PRESIDÊNCIA DO BRASIL] [CARGO: PRESIDENTE]\n");
        printf ("|\t*Sra. Maeli Gente Boa (nº17)\n");
        printf ("|\t*Sr. Antônio do Brasil (nº22)\n");
        printf ("|\t*Dr. Lissandro Progresso (nº31)\n");
        printf ("|\t*BRANCO: (Nº1)\n");
        printf ("|INFORME O Nº DA OPÇÃO ESCOLHIDA:\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        scanf ("%d", &Presidente);
        setbuf(stdin, NULL);

        if (Presidente == 1 || Presidente == 17 || Presidente == 22 || Presidente == 31)
        {
          puts ("---------------------------------------------------------------------------------------------");
          printf ("|DIGITE (Nº3) PARA CONFIRMAR SEU VOTO OU QUALQUER OUTRO PARA RETORNAR À VOTAÇÃO:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
        else
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|*ATENÇÃO:\n");
          printf ("|O NÚMERO DIGITADO CORRESPONDE A NENHUMA DAS ALTERNATIVAS DE VOTAÇÃO!\n");
          printf ("|SEU VOTO SERÁ CONSIDERADO COMO NULO!\n");
          printf ("|DIGITE (Nº2) PARA CORRIGIR E REFAZER A VOTAÇÃO OU (Nº3) PARA PROSSEGUIR:\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          scanf ("%d", &Confirma);
          setbuf(stdin, NULL);
          system ("cls");
        }
      }
      while (Confirma != 3);

      /*
      Nesta seção é feita a publicação com o espelho de votação de cada eleitor, sempre após o término de sua
      votação. Para cada categoria existe uma validação que é feita para apurar a qual candidato ou opção foi
      destinado o voto do eleitor vigente, esta validação é feita para publicar os nomes dos candidatos através
      do comando de saída printf.
      Nesta mesma seção, também é feita a incrementação das variáveis que serão usadas para a realização dos
      cálculos relacionados aos resultados da votação geral. Utiliza-se normalmente duas variáveis, uma para
      incrementar o voto do candidato e o outra para incrementar os votos válidos se for o caso, e ainda, nos
      casos de votos brancos e nulos é utiliada uma variável à parte. Aqui também é feita a publicação do título
      do eleitor vigente.
      Linhas 279 à 416.
      */
      do
      {
        printf ("---------------------------------------------------------------------------------------------\n");
        printf ("|ESPELHO DE VOTAÇÃO - RELATÓRIO PARCIAL:\n");
        printf ("|TÍTULO DO ELEITOR: %.lf\n", TituloEleitoral);
        printf ("|CONFIRA TODAS AS INFORMAÇÕES COM ATENÇÃO!\n");
        if (DepEstadual == 51)
        {
          printf ("|\t[Deputado Estadual] [Meu Voto: Candidato - Sra. Ana Rita Pacheco (nº%d)]\n", DepEstadual);
          AnaRita++;
          ValidosDepEstad++;
          Feminino++;
        }
        else if (DepEstadual == 34)
        {
          printf ("|\t[Deputado Estadual] [Meu Voto: Candidato - Sra. Ana Guilherme (nº%d)]\n", DepEstadual);
          AnaGui++;
          ValidosDepEstad++;
          Feminino++;
        }
        else if (DepEstadual == 11)
        {
          printf ("|\t[Deputado Estadual] [Meu Voto: Candidato - Sr. Adalberto Campos (nº%d)]\n", DepEstadual);
          Adalberto++;
          ValidosDepEstad++;
          Masculino++;
        }
        else if (DepEstadual == 1)
        {
          printf ("|\t[Deputado Estadual] [Meu Voto: BRANCO (nº%d]\n", DepEstadual);
          BrancosDepEstad++;
        }
        else
        {
          printf ("|\t[Deputado Estadual] [Meu Voto: NULO (nº%d)]\n", DepEstadual);
          NulosDepEstad++;
        }
        //--------------------------------------------------------------------------------------------------------;
        if (DepFederal == 56)
        {
          printf ("|\t[Deputado Federal] [Meu Voto: Candidato - Sra. Ana Vitória (nº%d)]\n", DepFederal);
          AnaVitoria++;
          ValidosDepFed++;
          Feminino++;
        }
        else if (DepFederal == 33)
        {
          printf ("|\t[Deputado Federal] [Meu Voto: Candidato - Sr. Paulo Guilherme (nº%d)]\n", DepFederal);
          PauloGui++;
          ValidosDepFed++;
          Masculino++;
        }
        else if (DepFederal == 1)
        {
          printf ("|\t[Deputado Federal] [Meu Voto: BRANCO (nº%d]\n", DepFederal);
          BrancosDepFed++;
        }
        else
        {
          printf ("|\t[Deputado Federal] [Meu Voto: NULO (nº%d)]\n", DepFederal);
          NulosDepFed++;
        }
        //---------------------------------------------------------------------------------------------------------;
        if (Senador == 4)
        {
          printf ("|\t[Senador] [Meu Voto: Candidato - Sr. Gutemberg Silva (nº%d)]\n", Senador);
          Gutemberg++;
          ValidosSenador++;
          Masculino++;
        }
        else if (Senador == 67)
        {
          printf ("|\t[Senador] [Meu Voto: Candidato - Sr. Fernando Fernandes (nº%d)]\n", Senador);
          Fernando++;
          ValidosSenador++;
          Masculino++;
        }
        else if (Senador == 1)
        {
          printf ("|\t[Senador] [Meu Voto: BRANCO (nº%d]\n", Senador);
          BrancosSenad++;
        }
        else
        {
          printf ("|\t[Senador] [Meu Voto: NULO (nº%d)]\n", Senador);
          NulosSenad++;
        }
        //---------------------------------------------------------------------------------------------------------;
        if (Governador == 38)
        {
          printf ("|\t[Governador] [Meu Voto: Candidato - Sr. Maia Da Ana (nº%d)]\n", Governador);
          MaiaDaAna++;
          ValidosGov++;
          Masculino++;
        }
        else if (Governador == 40)
        {
          printf ("|\t[Governador] [Meu Voto: Candidato - Sr. Gentil (nº%d)]\n", Governador);
          Gentil++;
          ValidosGov++;
          Masculino++;
        }
        else if (Governador == 18)
        {
          printf ("|\t[Governador] [Meu Voto: Candidato - Sra. Dona Selma Silva (nº%d)]\n", Governador);
          DonaSelma++;
          ValidosGov++;
          Feminino++;
        }
        else if (Governador == 1)
        {
          printf ("|\t[Governador] [Meu Voto: BRANCO (nº%d)]\n", Governador);
          BrancosGov++;
        }
        else
        {
          printf ("|\t[Governador] [Meu Voto: NULO (nº%d)]\n", Governador);
          NulosGov++;
        }
        //---------------------------------------------------------------------------------------------------------;
        if (Presidente == 17)
        {
          printf ("|\t[Presidente] [Meu Voto: Candidato - Sra. Maeli Gente Boa (nº%d)]\n", Presidente);
          Maeli++;
          ValidosPresid++;
          Feminino++;
        }
        else if (Presidente == 22)
        {
          printf ("|\t[Presidente] [Meu Voto: Candidato - Sr. Antônio do Brasil (nº%d)]\n", Presidente);
          AnBrasil++;
          ValidosPresid++;
          Masculino++;
        }
        else if (Presidente == 31)
        {
          printf ("|\t[Presidente] [Meu Voto: Candidato - Dr. Lissandro Progresso (nº%d)]\n", Presidente);
          Lissandro++;
          ValidosPresid++;
          Masculino++;
        }
        else if (Presidente == 1)
        {
          printf ("|\t[Presidente] [Meu Voto: BRANCO (nº%d)]\n", Presidente);
          BrancosPresid++;
        }
        else
        {
          printf ("|\t[Presidente] [Meu Voto: NULO (nº%d)]\n", Presidente);
          NulosPresid++;
        }
        //---------------------------------------------------------------------------------------------------------;
        /*
        Bloco desenvolvido para validar e confirmar finalmente as informações de votação de cada eleitor. Nas mensagens
        de saída abaixo, o usuário poderá decidir se deseja confirmar ou não as informãções publicadas no espelho.
        Caso ele não confirme, todas as variáveis possilvemente utilizadas serão decrementadas com uma "chuva" de ifs
        e elses utilizados para realizar o tratamento de erro desta seção do programa.
        Independente de qual opção o usuário escolher, após o término dos condicionais desta seção, ele retornará ao
        menu principal do programa, sendo que na segunda opção que é a de confirmar a votação, o programa fará todos
        os cálculos referentes a votação do eleitor. Para assegurar que a entrada do usuário seja correta, existe um
        else que garante que ele não entre com valores inválidos.
        Linhas 426 à 558.
        */
        printf ("|[TSEC - TRIBUNAL SUPERIOR DE ECOMP]\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        printf ("|TODAS AS INFORMAÇÕES ACIMA CONFEREM COM SUA VOTAÇÃO?\n");
        printf ("|\t[SE NÃO, DIGITE: Nº1 PARA REFAZER A VOTAÇÃO]\n");
        printf ("|\t[SE SIM, DIGITE: Nº2 PARA CONFIRMAR A VOTAÇÃO]\n");
        printf ("|ATENÇÃO: APÓS A CONFIRMAÇÃO DA VOTAÇÃO OS VOTOS NÃO PODERÃO SER ALTERADOS!\n");
        printf ("---------------------------------------------------------------------------------------------\n");
        scanf ("%d", &OpcaoMenu);
        setbuf(stdin, NULL);
        system ("pause");
        system ("cls");

        if (OpcaoMenu == 1)
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|VOCÊ SERÁ REDIRECIONADO AO MENU PRINCIPAL:\n");
          printf ("|ESCOLHA A OPÇÃO (Nº1) PARA REFAZER A VOTAÇÃO!\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          system ("pause");
          system ("cls");
          if (ContadorEleitores<AnaRita)
          {
            AnaRita--;
            ValidosDepEstad--;
            Feminino--;
          }
          else if (ContadorEleitores<AnaGui)
          {
            AnaGui--;
            ValidosDepEstad--;
            Feminino--;
          }
          else if (ContadorEleitores<Adalberto)
          {
            Adalberto--;
            ValidosDepEstad--;
            Masculino--;
          }
          else if (ContadorEleitores<BrancosDepEstad)
          {
            BrancosDepEstad--;
          }
          else
          {
            NulosDepEstad--;
          }
          //---------------------------------------------------------------------------------------------------------;
          if (ContadorEleitores<AnaVitoria)
          {
            AnaVitoria--;
            ValidosDepFed--;
            Feminino--;
          }
          else if (ContadorEleitores<PauloGui)
          {
            PauloGui--;
            ValidosDepFed--;
            Masculino--;
          }
          else if (ContadorEleitores<BrancosDepFed)
          {
            BrancosDepFed--;
          }
          else
          {
            NulosDepFed--;
          }
          //---------------------------------------------------------------------------------------------------------;
          if (ContadorEleitores<Gutemberg)
          {
            Gutemberg--;
            ValidosSenador--;
            Masculino--;
          }
          else if (ContadorEleitores<Fernando)
          {
            Fernando--;
            ValidosSenador--;
            Masculino--;
          }
          else if (ContadorEleitores<BrancosSenad)
          {
            BrancosSenad--;
          }
          else
          {
            NulosSenad--;
          }
          //---------------------------------------------------------------------------------------------------------;
          if (ContadorEleitores<MaiaDaAna)
          {
            MaiaDaAna--;
            ValidosGov--;
            Masculino--;
          }
          else if (ContadorEleitores<Gentil)
          {
            Gentil--;
            ValidosGov--;
            Masculino--;
          }
          else if (ContadorEleitores<DonaSelma)
          {
            DonaSelma--;
            ValidosGov--;
            Feminino--;
          }
          else if (ContadorEleitores<BrancosGov)
          {
            BrancosGov--;
          }
          else
          {
            NulosGov--;
          }
          //--------------------------------------------------------------------------------------------------------;
          if (ContadorEleitores<Maeli)
          {
            Maeli--;
            ValidosPresid--;
            Feminino--;
          }
          else if (ContadorEleitores<AnBrasil)
          {
            AnBrasil--;
            ValidosPresid--;
            Masculino--;
          }
          else if (ContadorEleitores<Lissandro)
          {
            Lissandro--;
            ValidosPresid--;
            Masculino--;
          }
          else if (ContadorEleitores<BrancosPresid)
          {
            BrancosPresid--;
          }
          else
          {
            NulosPresid--;
          }
        }
        /*
        Neste bloco, como falado no comentário anterior, os cálculos de porcentagens serão executados se o usuário
        confirmar a votação. O cálculo funciona da seguinte forma: os votos de cada candidato são obviamente
        multiplicados por 100 e divididos pela variável responsável por guardar todos os votos válidos em cada categoria.
        Os votos nulos e brancos são multiplicados por 100 e divididos pela quantidade de eleitores porque entende-se
        que se o usuário não escolheu nenhum dos candidatos, ele só pôde votar em branco ou nulo, sendo assim, é seguro
        calcular a porcentagem dos votos nulos e brancos dividindo pela quantidade de eleitores.
        Linhas 569 à 611.
        */
        else if (OpcaoMenu == 2)
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("|SUA VOTAÇÃO FOI CONFIRMADA COM SUCESSO!\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          system ("pause");
          system ("cls");
          ContMascFem= ContMascFem + Feminino + Masculino;
          ContadorEleitores++;
          PorcentAnaRita = (AnaRita*100)/(float)ValidosDepEstad;
          PorcentAnaGui = (AnaGui*100)/(float)ValidosDepEstad;
          PorcentAdalberto = (Adalberto*100)/(float)ValidosDepEstad;
          PorcentAnaVitoria = (AnaVitoria*100)/(float)ValidosDepFed;
          PorcentPauloGui = (PauloGui*100)/(float)ValidosDepFed;
          PorcentGutemberg = (Gutemberg*100)/(float)ValidosSenador;
          PorcentFernando = (Fernando*100)/(float)ValidosSenador;
          PorcentMaiaDaAna = (MaiaDaAna*100)/(float)ValidosGov;
          PorcentGentil = (Gentil*100)/(float)ValidosGov;
          PorcentDonaSelma = (DonaSelma*100)/(float)ValidosGov;
          PorcentMaeli = (Maeli*100)/(float)ValidosPresid;
          PorcentAnBrasil = (AnBrasil*100)/(float)ValidosPresid;
          PorcentLissandro = (Lissandro*100)/(float)ValidosPresid;
          PorcentBrancosDepEst = (BrancosDepEstad*100)/(float)ContadorEleitores;
          PorcentNulosDepEst = (NulosDepEstad*100)/(float)ContadorEleitores;
          PorcentBrancosDepFed = (BrancosDepFed*100)/(float)ContadorEleitores;
          PorcentNulosDepFed = (NulosDepFed*100)/(float)ContadorEleitores;
          PorcentBrancosSenad = (BrancosSenad*100)/(float)ContadorEleitores;
          PorcentNulosSenad = (NulosSenad*100)/(float)ContadorEleitores;
          PorcentBrancosGov = (BrancosGov*100)/(float)ContadorEleitores;
          PorcentNulosGov = (NulosGov*100)/(float)ContadorEleitores;
          PorcentBrancosPresid = (BrancosPresid*100)/(float)ContadorEleitores;
          PorcentNulosPresid = (NulosPresid*100)/(float)ContadorEleitores;
          PercentFeminino = (Feminino*100)/(float)ContMascFem;
          PercentMasculino = (Masculino*100)/(float)ContMascFem;
        }
        else //Tratamento de erro citado no penúltimo comentário.
        {
          printf ("---------------------------------------------------------------------------------------------\n");
          printf ("O NÚMERO DIGITADO NÃO CORRESPONDE A UMA DAS OPÇÕES VÁLIDAS!\n");
          printf ("TENTE NOVAMENTE!\n");
          printf ("---------------------------------------------------------------------------------------------\n");
          system ("pause");
          system ("cls");
        }
      }
      while (OpcaoMenu != 2 && OpcaoMenu != 1);
      break;
    /*
    Este bloco é responsável por publicar o relatório final com todos dados finais da votação geral, o usuário poderá
    acessar estas informações inserindo a opção "2" no menu principal e só poderá consultá-lo após existir pelo menos
    os votos de um eleitor registrado, para que não haja erros com cálculos indeterminados.
    Aqui são publicados a quantidade de eleitores, a quantidade de votos em cada candidato, bem como sua porcentagem,
    separadamente por categoria.
    Além disso, também são publicados a quantidade de votos brancos e nulos juntamente com suas respectivas porcentagens
    e, os votos em candidadatos do sexo feminino e masculino.
    Linhas 622 à 759.
    */
    case 2:
      if (ContadorEleitores>0)
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|RESULTADO FINAL - DADOS ESTATÍSTICOS DA VOTAÇÃO:\n");
        printf ("|TOTAL DE ELEITORES: [%d]\n", ContadorEleitores);
        printf ("|TOTAL E PERCENTUAL DE VOTOS VÁLIDOS EM CADA CANDIDATO (AGRUPADO POR CARGO):\n");
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - DEPUTADO ESTADUAL:\n");
        printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosDepEstad);
        printf ("|\tDra. Ana Rita Pacheco (nº51): [%d votos!] - [%.2f%%]\n", AnaRita, PorcentAnaRita);
        printf ("|\tSra. Ana Guilherme (nº34): [%d votos!] - [%.2f%%]\n", AnaGui, PorcentAnaGui);
        printf ("|\tSr. Adalberto Campos (nº11): [%d votos!] - [%.2f%%]\n", Adalberto, PorcentAdalberto);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - DEPUTADO FEDERAL:\n");
        printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosDepFed);
        printf ("|\tSra. Ana Vitória (nº56): [%d votos!] - [%.2f%%]\n", AnaVitoria, PorcentAnaVitoria);
        printf ("|\tSr. Paulo Guilherme (nº33): [%d votos!] - [%.2f%%]\n", PauloGui, PorcentPauloGui);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - SENADOR:\n");
        printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosSenador);
        printf ("|\tSr. Gutemberg Silva (nº4): [%d votos!] - [%.2f%%]\n", Gutemberg, PorcentGutemberg);
        printf ("|\tSr. Fernando Fernandes (nº67): [%d votos!] - [%.2f%%]\n", Fernando, PorcentFernando);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - GOVERNADOR:\n");
        printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosGov);
        printf ("|\tSr. Maia da Ana (nº38): [%d votos!] - [%.2f%%]\n", MaiaDaAna, PorcentMaiaDaAna);
        printf ("|\tSr. Gentil (nº40): [%d votos!] - [%.2f%%]\n", Gentil, PorcentGentil);
        printf ("|\tSra. Dona Selma (nº18): [%d votos!] - [%.2f%%]\n", DonaSelma, PorcentDonaSelma);
        puts ("---------------------------------------------------------------------------------------------");
        if (Maeli > (ValidosPresid/2) || AnBrasil > (ValidosPresid/2) || Lissandro > (ValidosPresid/2))
        {
          printf ("|CATEGORIA - PRESIDENTE:\n");
          printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosPresid);
          printf ("|\tSra. Maeli Gente Boa (nº17): [%d votos!] - [%.2f%%]\n", Maeli, PorcentMaeli);
          printf ("|\tSr. Antônio Brasil (nº22): [%d votos!] - [%.2f%%]\n", AnBrasil, PorcentAnBrasil);
          printf ("|\tSra. Lissandro Progresso (nº31): [%d votos!] - [%.2f%%]\n", Lissandro, PorcentLissandro);
          puts ("---------------------------------------------------------------------------------------------");
          system ("pause");
          system ("cls");
        }
        else if (Maeli > AnBrasil && AnBrasil > Lissandro)
        {
          printf ("|CATEGORIA - PRESIDENTE:\n");
          printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosPresid);
          printf ("|\tSra. Maeli Gente Boa (nº17): [%d votos!] - [%.2f%%]\n", Maeli, PorcentMaeli);
          printf ("|\tSr. Antônio Brasil (nº22): [%d votos!] - [%.2f%%]\n", AnBrasil, PorcentAnBrasil);
          printf ("|\tSra. Lissandro Progresso (nº31): [%d votos!] - [%.2f%%]\n", Lissandro, PorcentLissandro);
          printf ("|NENHUM DOS CANDIDATOS ATINGIU MAIS QUE 50%% DOS VOTOS, PORTANTO:\n");
          printf ("|MAELI GENTE BOA (Nº17) E ANTÔNIO BRASIL (Nº22) CONCORRERÃO EM SEGUNDO TURNO!\n");
          puts ("---------------------------------------------------------------------------------------------");
          system ("pause");
          system ("cls");
        }
        else if (Maeli > Lissandro && Lissandro > AnBrasil)
        {
          printf ("|CATEGORIA - PRESIDENTE:\n");
          printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosPresid);
          printf ("|\tSra. Maeli Gente Boa (nº17): [%d votos!] - [%.2f%%]\n", Maeli, PorcentMaeli);
          printf ("|\tSr. Antônio Brasil (nº22): [%d votos!] - [%.2f%%]\n", AnBrasil, PorcentAnBrasil);
          printf ("|\tSra. Lissandro Progresso (nº31): [%d votos!] - [%.2f%%]\n", Lissandro, PorcentLissandro);
          printf ("|NENHUM DOS CANDIDATOS ATINGIU MAIS QUE 50%% DOS VOTOS, PORTANTO:\n");
          printf ("|MAELI GENTE BOA (Nº17) E LISSANDRO PROGRESSO (Nº31) CONCORRERÃO EM SEGUNDO TURNO!\n");
          puts ("---------------------------------------------------------------------------------------------");
          system ("pause");
          system ("cls");
        }
        else if (Lissandro > AnBrasil && AnBrasil > Maeli)
        {
          printf ("|CATEGORIA - PRESIDENTE:\n");
          printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosPresid);
          printf ("|\tSra. Maeli Gente Boa (nº17): [%d votos!] - [%.2f%%]\n", Maeli, PorcentMaeli);
          printf ("|\tSr. Antônio Brasil (nº22): [%d votos!] - [%.2f%%]\n", AnBrasil, PorcentAnBrasil);
          printf ("|\tSra. Lissandro Progresso (nº31): [%d votos!] - [%.2f%%]\n", Lissandro, PorcentLissandro);
          printf ("|NENHUM DOS CANDIDATOS ATINGIU MAIS QUE 50%% DOS VOTOS, PORTANTO:\n");
          printf ("|ANTÔNIO BRASIL (Nº22) E LISSANDRO PROGRESSO (Nº31) CONCORRERÃO EM SEGUNDO TURNO!\n");
          puts ("---------------------------------------------------------------------------------------------");
          system ("pause");
          system ("cls");
        }
        else
        {
          printf ("|CATEGORIA - PRESIDENTE:\n");
          printf ("|TOTAL DE VOTOS VÁLIDOS NESTA CATEGORIA: [%d votos!]\n", ValidosPresid);
          printf ("|\tSra. Maeli Gente Boa (nº17): [%d votos!] - [%.2f%%]\n", Maeli, PorcentMaeli);
          printf ("|\tSr. Antônio Brasil (nº22): [%d votos!] - [%.2f%%]\n", AnBrasil, PorcentAnBrasil);
          printf ("|\tSra. Lissandro Progresso (nº31): [%d votos!] - [%.2f%%]\n", Lissandro, PorcentLissandro);
          puts ("---------------------------------------------------------------------------------------------");
          system ("pause");
          system ("cls");
        }
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|RESULTADO FINAL - DADOS ESTATÍSTICOS DA VOTAÇÃO:\n");
        printf ("|TOTAL E PERCENTUAL DE VOTOS BRANCOS E NULOS EM CADA CATEGORIA:\n");
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - DEPUTADO ESTADUAL:\n");
        printf ("|TOTAL DE VOTOS BRANCOS: [%d votos!] - [%.2f%%]\n", BrancosDepEstad, PorcentBrancosDepEst);
        printf ("|TOTAL DE VOTOS NULOS: [%d votos!] - [%.2f%%]\n", NulosDepEstad, PorcentNulosDepEst);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - DEPUTADO FEDERAL:\n");
        printf ("|TOTAL DE VOTOS BRANCOS: [%d votos!] - [%.2f%%]\n", BrancosDepFed, PorcentBrancosDepFed);
        printf ("|TOTAL DE VOTOS NULOS: [%d votos!] - [%.2f%%]\n", NulosDepFed, PorcentNulosDepFed);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - SENADOR:\n");
        printf ("|TOTAL DE VOTOS BRANCOS: [%d votos!] - [%.2f%%]\n", BrancosSenad, PorcentBrancosSenad);
        printf ("|TOTAL DE VOTOS NULOS: [%d votos!] - [%.2f%%]\n", NulosSenad, PorcentNulosSenad);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - GOVERNADOR:\n");
        printf ("|TOTAL DE VOTOS BRANCOS: [%d votos!] - [%.2f%%]\n", BrancosGov, PorcentBrancosGov);
        printf ("|TOTAL DE VOTOS NULOS: [%d votos!] - [%.2f%%]\n", NulosGov, PorcentNulosGov);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|CATEGORIA - PRESIDENTE:\n");
        printf ("|TOTAL DE VOTOS BRANCOS: [%d votos!] - [%.2f%%]\n", BrancosPresid, PorcentBrancosPresid);
        printf ("|TOTAL DE VOTOS NULOS: [%d votos!] - [%.2f%%]\n", NulosPresid, PorcentNulosPresid);
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|TOTAL E PERCENTUAL DE VOTOS EM CANDIDATOS DO SEXO MASCULINO E DO SEXO FEMININO:\n");
        printf ("|\tCANDIDATOS DO SEXO MASCULINO: [%d votos!] [%.2f%%]\n", Masculino, PercentMasculino);
        printf ("|\tCANDIDATOS DO SEXO FEMININO: [%d votos!] [%.2f%%]\n", Feminino, PercentFeminino);
        puts ("---------------------------------------------------------------------------------------------");
        system ("pause");
        system ("cls");
      }
      else //Tratamento de erro citado no comentário anterior.
      {
        puts ("---------------------------------------------------------------------------------------------");
        printf ("|NENHUM VOTO FOI REGISTRADO, NÃO HÁ RESULTADOS PARA EXIBIR!\n");
        puts ("---------------------------------------------------------------------------------------------");
        system ("pause");
        system ("cls");
      }
      break;

    case 3: //Comando para finalização do programa.
      puts ("---------------------------------------------------------------------------------------------");
      printf ("|PROGRAMA FINALIZADO!\n");
      puts ("---------------------------------------------------------------------------------------------");
      system ("pause");
      system ("cls");
      break;

    default: //Tratamento de erro para valores inválidos inseridos no menu do programa.
      puts ("---------------------------------------------------------------------------------------------");
      printf ("|ERRO! TENTE NOVAMENTE!\n");
      puts ("---------------------------------------------------------------------------------------------");
      system ("pause");
      system ("cls");
      break;
    }
  }
  while (OpcaoMenu != 3);

  return 0;
}
