package chatbot;
//////////////////////////////////////////////////////////////////////////////////////////////////
import java.util.Scanner;
import java.util.Calendar;
//////////////////////////////////////////////////////////////////////////////////////////////////
class Bot {
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void horaDia() {//									Método ou função, chamada horaDia(), serve pra cumprimentar o usuario durante o atendimento
		Calendar calendario = Calendar.getInstance();//			(Classe="Calendar" variável="calendario") =  (Classe="Calendar" . comando"getInstance(), este comando pega o fusohorario padrão local ")
		int hora = calendario.get(Calendar.HOUR_OF_DAY);// ([Tipo da variavel] [nome da variavel] = variavel calendario.(função"get"(Classe "Calendar". campo(Hora_do_dia)))), essa variavel vai se chamar "hora" e vai pegar as especificações de calendario, vai funcionar como apenas numeros inteiros, e aparecer de acordo com o horario do meu sistema, mas apenas os dois primeiros digitos
		//System.out.println("Data/Hora atual: "+hora);
		if (hora > 0 && hora <= 12) {// 					Se a hora do meu sistema estiver entre 1 e 12, vai aparecer "Bom dia: "
			System.out.print("Bom dia: ");}
		else if (hora > 12 && hora <=18) {//			Se a hora do meu sistema estiver entre 13 e 18, vai aparecer "Boa tarde: "
			System.out.print("Boa tarde: ");}
		else if (hora > 18 && hora <=23) {//			Se a hora do meu sistema estiver entre 19 e 23, vai aparecer "Boa noite: "
			System.out.print("Boa noite: ");}
		else if (hora == 0) {//								Se a hora do meu sistema estiver em 0, vai aparecer "Boa Noite: "
			System.out.print("Boa noite: ");}
		else {System.out.println("Não entendi que horas são ");}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void resposta1invalida() {//				Caso a pessoa digite uma opção invalida, vai aparecer esta mensagem
		System.out.println("Resposta Inválida, ");
		System.out.println("por favor, digite uma reposta válida!");}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void resposta2invalida() {//				Caso a pessoa não digite nada e confirme o envio, aparecerá uma mensagem
		System.out.println("Resposta inválida, ");
		System.out.println("Por favor digite novamente a opção escolhida");}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void nomeINFO() {//							Método que serve para saber o nome do cliente em questão
		Scanner in = new Scanner(System.in);//	Função "Scanner" e de recurso "in" que seria para a entrada de dados, new "novo", método Scanner(Onde irá atuar"System", e onde terá influencia"in" que é a entrada de dados")
		String clienteNome;//							Tipo da variável, nome da variavel, deixa nula , pois depois será atribuida dados a ela
		System.out.println("Qual é o seu nome ? ");
		clienteNome = in.nextLine();//				Variavel = in"entrada de dados", quando irá acontecer, "nextLine();" quando a pessoa digitar algo, será atribuida a variavel clienteNome"
		if (clienteNome.equals("") || (clienteNome.equals("[")) || (clienteNome.equals("]")) || (clienteNome.equals(".")) || (clienteNome.equals(",")))  {
			System.out.println("Por favor, informe seu nome");
			nomeINFO();}
		else {
			horaDia();//										Método horaDia() que serve para checar que horas está no sistema e dar uma mensagem a partir disso
			System.out.println(""+clienteNome+"! ");//  Mensagem de que horas a pessoa está + o nome que ela escreveu, EX: "Boa tarde: Alexandre de Morais"
		}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp1() {
		Scanner in = new Scanner(System.in);
		String atendimento1p1;
		System.out.println("");
		System.out.println("Você escolheu, "+"Já sou cliente Rennovari");
		System.out.println("Você será redirecionado para nossa Secretaria");
		System.out.println("Aguarde a chamada de um dos nossos atendentes");
		System.out.println("");
		System.out.println("Clique e confirme para continuar o atendimento.");
		System.out.println("1 = Deseja continuar no Whatsapp ");
		System.out.println("2 = Fazer uma ligação ");
		System.out.println("");
		System.out.println("0 = Voltar ao inicio ");
		atendimento1p1 = in.nextLine();
		if (atendimento1p1.equals("1")) {
			System.out.println("");
			System.out.println("Aguarde e logo lhe retornaremos");}
		else if (atendimento1p1.equals("2")) {
			System.out.println("");
			System.out.println("Encaminhando chamada");
			System.out.println("Aguarde...");}
		else if (atendimento1p1.equals("0")) {
			atendimentoMain();}
		else {resposta1invalida();atendimentoOp1();}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp2() {
		Scanner in = new Scanner(System.in);
		String atendimentoOp2, visitaOuN;
		System.out.println("");
		System.out.println("Quem somos ?");
		System.out.println("Somos uma Creche e Pré-Escola licenciada e autorizada pelos órgãos ");
		System.out.println("competentes e contamos com uma equipe experiente e afetuosa.");
		System.out.println("Recebemos crianças a partir de 1 ano e 3 meses até os 5 anos (completos em 31 de março de 2023).");
		System.out.println("");
		System.out.println("Funcionamos no mesmo endereço há sete anos trabalhando o desenvolvimento, o convívio e os cuidados, com afeto e respeito.");
		System.out.println("Nossa estrutura confere segurança e liberdade às nossas turminhas, pois o nosso conceito é de que a creche inteira é uma grande sala de aula!");
		System.out.println("Contamos com espaços bem equipados e seguimos todos os protocolos de segurança.");
		System.out.println("Seja bem-vindo! Para continuarmos, digite o NÚMERO da opção deseja e clique ENVIAR.");
		System.out.println("");
		System.out.println("1 = Quero mais informações para o ano letivo de 2023");
		System.out.println("2 = Quero agendar uma visita");
		System.out.println("3 = Quero saber mais!");
		System.out.println("");
		System.out.println("0 = Opções iniciais ");
		atendimentoOp2 = in.nextLine();
		if (atendimentoOp2.equals("0")) {atendimentoMain();}
		else if (atendimentoOp2.equals("2")) {
			System.out.println("");
			System.out.println("Aguarde a chamada de um dos nossos atendentes");
			System.out.println("");
			System.out.println("Clique e confirme para continuar o atendimento.");
			System.out.println("1 = Deseja continuar no Whatsapp ");
			System.out.println("2 = Fazer uma ligação ");
			System.out.println("");
			System.out.println("0 = Opções iniciais ");
			System.out.println("9 = Voltar");
			visitaOuN = in.nextLine();
			if (visitaOuN.equals("1")) {
				System.out.println("");
				System.out.println("Aguarde e logo lhe retornaremos");}
			else if (visitaOuN.equals("2")) {
				System.out.println("");
				System.out.println("Encaminhando chamada");
				System.out.println("Aguarde...");}
			else if (visitaOuN.equals("0")) {atendimentoMain();}
			else if (visitaOuN.equals("9")) {atendimentoOp2();}
			}
		else if (atendimentoOp2.equals("3")) {
			atendimentoOp2p3();}
		else if (atendimentoOp2.equals("1")) {
			atendimentoOp2p1();}
		else if (atendimentoOp2.equals("")) {resposta1invalida();atendimentoOp2();}
		else {resposta1invalida();atendimentoOp2();}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp2p1() {
		Scanner in = new Scanner(System.in);
		String atendimentoOp2p1p, sairOuN, sairOuN2, sairOuN3, sairOuN4, sairOuN5, sairOuN6;
		System.out.println("");
		System.out.println("Ok! Preciso saber a idade que a sua criança terá em 31 de março de 2022.");
		System.out.println("A partir daí saberei a turma correta e os valores para lhe apresentar");
		System.out.println("");
		System.out.println("Para continuarmos, digite o NÚMERO da opção deseja e clique ENVIAR.");
		System.out.println("1) Minha criança ainda terá menos que 2 anos em 31 de março de 2023");
		System.out.println("2) Minha criança terá 2 anos completos em 31 de março de 2023");
		System.out.println("3) Minha criança terá 3 anos completos em 31 de março de 2023");
		System.out.println("4) Minha criança terá 4 anos completos em 31 de março de 2023");
		System.out.println("5) Minha criança terá 5 anos completos em 31 de março de 2023");
		System.out.println("6) Preciso de reforço escolar");
		System.out.println("");
		System.out.println("0 = Opções iniciais");
		System.out.println("9 = Voltar");
		atendimentoOp2p1p = in.nextLine();
		if (atendimentoOp2p1p.equals("0")) {atendimentoMain();}
		else if (atendimentoOp2p1p.equals("")) {resposta1invalida();atendimentoOp2p1();}
		else if (atendimentoOp2p1p.equals("9")) {atendimentoOp2();}
		else if (atendimentoOp2p1p.equals("1")) {
			System.out.println("");
			System.out.println("Oferecemos para o Pré-Maternal os seguintes horários:\n");
			System.out.println("MEIO PERÍODO");
			System.out.println("Matutino: Entrada às 7h / Saída às 11h *lanche não incluso");
			System.out.println("Vespertino: Entrada às 13h / Saída às 17h *lanche não incluso\n");
			
			System.out.println("PERÍODO INTEGRAL");
			System.out.println("Entrada às 7h/ Saída às 17h");
			System.out.println("O Integral inclui: lanche da manhã, almoço, lanche da tarde e");
			System.out.println("caldinho\n");
			System.out.println("Temos ainda a opção de horário SEMI-INTEGRAL:");
			System.out.println(" 7h às 13h* Inclui almoço e lanche da manhã");
			System.out.println("");
			System.out.println("0 = Opções iniciais");
			System.out.println("9 = Voltar");
			sairOuN = in.nextLine();
			if (sairOuN.equals("0")) {atendimentoMain();}
			else if (sairOuN.equals("9")) {atendimentoOp2p1();}
			else if (sairOuN.equals("")) {resposta2invalida();atendimentoOp2p1();}
		}else if (atendimentoOp2p1p.equals("2"+ "") || (atendimentoOp2p1p.equals("3"+""))) {
			System.out.println("");
			
			System.out.println("A sua criança tem idade para as nossas turmas de Maternal I  (2 anos completos) ou Maternal II (3 anos completos) ");
			System.out.println("nossas turmas são de no máximo 12 crianças acompanhadas diretamente por uma professora e uma monitora/estagiária.");
			System.out.println("Oferecemos para os Maternais os seguintes horários:\n");
			System.out.println("MEIO PERÍODO");
			System.out.println("Matutino: Entrada às 7h / Saída às 11h *lanche não incluso");
			System.out.println("Vespertino: Entrada às 13h / Saída às 17h *lanche não incluso\n");
			System.out.println("INTEGRAL");
			System.out.println("O Integral inclui: almoço, lanche da tarde e");
			System.out.println("caldinho");
			System.out.println("Entrada às 7h / Saída às 17h\n");
			System.out.println("Temos ainda a opção de horário SEMI-INTEGRAL:");
			System.out.println(" 7h às 13h* Inclui almoço.");
			System.out.println("");
			System.out.println("0 = Opções iniciais");
			System.out.println("9 = Voltar");
			sairOuN2 = in.nextLine();
			if (sairOuN2.equals("0")) {atendimentoMain();}
			else if (sairOuN2.equals("9")) {atendimentoOp2p1();}
			else if (sairOuN2.equals("")) {resposta2invalida();atendimentoOp2p1();}}
			else if (atendimentoOp2p1p.equals("3")) {
				System.out.println("");
				System.out.println("A sua criança tem idade para as nossas turmas de Jardiml I  (4 anos completos) ou Jardim II (5 anos completos)");
				System.out.println("nossas turmas são de no máximo 12 crianças acompanhadas diretamente por uma professora.\n");
				System.out.println("MEIO PERÍODO	");
				System.out.println("Oferecemos para os Jardins os seguintes horários:");
				System.out.println("Matutino: Entrada às 7h / Saída às 11h *lanche não incluso");
				System.out.println("Vespertino: Entrada às 13h / Saída às 17h *lanche não incluso");
				System.out.println("Período Integral: Entrada às 7h / Saída às 17h");
				System.out.println("O Integral inclui almoço, lanche da tarde e caldinho (antes da saída)");
				System.out.println("Temos ainda a opção de Semi-Integral: 7h às 13h ou 11h às 17h");
				System.out.println("O semi-integral inclui somente o almoço");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				sairOuN3 = in.nextLine();
				if (sairOuN3.equals("0")) {atendimentoMain();}
				else if (sairOuN3.equals("9")) {atendimentoOp2p1();}
				else if (sairOuN3.equals("")) {resposta2invalida();atendimentoOp2p1();}}
				else if (atendimentoOp2p1p.equals("4")) {
					System.out.println("");
					System.out.println("A sua criança tem idade para as nossas turmas de Jardiml I  (4 anos completos) ou Jardim II (5 anos completos)");
					System.out.println("nossas turmas são de no máximo 12 crianças acompanhadas diretamente por uma professora.");
					System.out.println("");
					System.out.println("Oferecemos para os Jardins os seguintes horários:\n");
					System.out.println("MEIO PERÍODO");
					System.out.println("Matutino: Entrada às 7h / Saída às 11h *lanche não incluso");
					System.out.println("Vespertino: Entrada às 13h / Saída às 17h *lanche não incluso\n");
					System.out.println("PERÍODO INTEGRAL: Entrada às 7h / Saída às 17h");
					System.out.println("O Integral inclui almoço, lanche da tarde e caldinho (antes da saída)\n");
					System.out.println("Temos ainda a opção de SEMI-INTEGRAL: 7h às 13h ou 11h às 17h");
					System.out.println("O semi-integral inclui somente o almoço");
					System.out.println("");
					System.out.println("0 = Opções iniciais");
					System.out.println("9 = Voltar");
					sairOuN4 = in.nextLine();
					if (sairOuN4.equals("0")) {atendimentoMain();}
					else if (sairOuN4.equals("9")) {atendimentoOp2p1();}
					else if (sairOuN4.equals("")) {resposta2invalida();atendimentoOp2p1();}
				}
					else if (atendimentoOp2p1p.equals("5")) {
						System.out.println("");
						System.out.println("A sua criança tem idade para as nossas turmas de Jardiml I  (4 anos completos) ou Jardim II (5 anos completos)");
						System.out.println("nossas turmas são de no máximo 12 crianças acompanhadas diretamente por uma professora.");
						System.out.println("");
						System.out.println("Oferecemos para os Jardins os seguintes horários:\n");
						System.out.println("MEIO PERÍODO");
						System.out.println("Matutino: Entrada às 7h / Saída às 11h *lanche não incluso");
						System.out.println("Vespertino: Entrada às 13h / Saída às 17h *lanche não incluso\n");
						System.out.println("PERÍODO INTEGRAL: Entrada às 7h / Saída às 17h");
						System.out.println("O Integral inclui almoço, lanche da tarde e caldinho (antes da saída)\n");
						System.out.println("Temos ainda a opção de SEMI-INTEGRAL: 7h às 13h ou 11h às 17h");
						System.out.println("O semi-integral inclui somente o almoço");
						System.out.println("");
						System.out.println("0 = Opções iniciais");
						System.out.println("9 = Voltar");
						sairOuN5 = in.nextLine();
						if (sairOuN5.equals("0")) {atendimentoMain();}
						else if (sairOuN5.equals("9")) {atendimentoOp2p1();}
						else if (sairOuN5.equals("")) {resposta2invalida();atendimentoOp2p1();}
						}
						else if (atendimentoOp2p1p.equals("6")) {
							System.out.println("");
							System.out.println("Se você precisa que a sua criança tenha auxílio nas atividades escolares,");
							System.out.println("cuidados pessoais e muito convívio e carinho, temos a opção do Reforço no contraturno");
							System.out.println("em que a criança estuda. Nessa modalidade atendemos de 3 a 6 anos completos em 31 ");
							System.out.println("de Março do 2023.");
							System.out.println("");
							System.out.println("Matutino: Entrada às 7h / Saída às 11h");
							System.out.println("Vespertino: Entrada às 13h / Saída às 17h\n");
							System.out.println("Temos ainda a opção de SEMI-INTEGRAL: 7h às 13h ou 11h às 17h");
							System.out.println("O semi-integral inclui somente o almoço. Lanche não incluso");
							System.out.println("");
							System.out.println("0 = Opções iniciais");
							System.out.println("9 = Voltar");
							sairOuN6 = in.nextLine();
							if (sairOuN6.equals("0")) {atendimentoMain();}
							else if (sairOuN6.equals("9")) {atendimentoOp2p1();}
							else if (sairOuN6.equals("")) {resposta2invalida();atendimentoOp2p1();}
						}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp2p3() {
		String atendimentoOp2p3op, ficarOuN, ficarOuN2, ficarOuN3, visitaSN ;
		Scanner in = new Scanner(System.in);
		System.out.println("");
		System.out.println("Para continuarmos, digite o NÚMERO da opção deseja e clique ENVIAR.");
		System.out.println("1 = Quero agendar uma visita");
		System.out.println("2 = Quero saber valores e condições");
		System.out.println("3 = Quero saber a rotina e o método");
		System.out.println("4 = Quero saber sobre materiais da lista e livros didáticos");
		System.out.println("");
		System.out.println("0 = Opções iniciais");
		System.out.println("9 = Voltar");
		atendimentoOp2p3op = in.nextLine();
		if (atendimentoOp2p3op.equals("0")) {atendimentoMain();}
		else if (atendimentoOp2p3op.equals("9")) {atendimentoOp2();}
		else if (atendimentoOp2p3op.equals("1")) {
			System.out.println("");
			System.out.println("AGENDAR UMA VISITA");
			System.out.println("Você será redirecionado para nossa Secretaria!");
			System.out.println("Aguarde a chamada de um dos nossos atendentes");
			System.out.println("Clique e confirme para continuar o atendimento.");
			System.out.println("1 = Deseja continuar no Whatsapp"); 
			System.out.println("2 = Fazer uma ligação");
			System.out.println("");
			System.out.println("0 = Voltar ao inicio ");
			System.out.println("9 = Voltar");
			visitaSN = in.nextLine();
			if (visitaSN.equals("1")) {
				System.out.println("");
				System.out.println("Aguarde e logo lhe retornaremos");}
			else if (visitaSN.equals("2")) {
				System.out.println("");
				System.out.println("Encaminhando chamada");
				System.out.println("Aguarde...");}
			else if (visitaSN.equals("9")) {atendimentoOp2p3();}
			else if (visitaSN.equals("0")) {atendimentoMain();}
			}
		else if (atendimentoOp2p3op.equals("2")) {
			System.out.println("");
			System.out.println("VALORES E CONDIÇÕES");
				System.out.println("");
				System.out.println("			VALORES PARA 2023");
				System.out.println("								   	  Sem desconto		Com desconto");
				System.out.println("					Meio Período		      626,75		     599,50");
				System.out.println("PRÉ-MATERNAL	                Semi Integral		    1.058,00		   1.012,00");
				System.out.println("					Integral			    1.564,00		   1.496,00");
				System.out.println("");
				System.out.println("					Meio Período		      546,25		     522,50");
				System.out.println("MATERNAL I e II	        Semi Integral		      943,00		     902,00");
				System.out.println("					Integral			    1.322,50		   1.265,00");
				System.out.println("");
				System.out.println("					Meio Período		      523,25		     500,50");
				System.out.println("JARDIM I e II			Semi Integral		      943,00		     902,00");
				System.out.println("					Integral			    1.322,50		  1.265,00");
				System.out.println("");
				System.out.println("					Contraturno		      523,25		     500,50");
				System.out.println("REFORÇO");
				System.out.println("					Integral			      943,00		     902,00");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarOuN = in.nextLine();
					if (ficarOuN.equals("0")) {atendimentoMain();}
					else if (ficarOuN.equals("9")) {atendimentoOp2p3();}
		}else if (atendimentoOp2p3op.equals("3")) {
			System.out.println("");
			System.out.println("ROTINAS");
			System.out.println(" A partir das 7h nossas crianças chegam e são acolhidas. Às 7:30h temos a roda de conversa com música e dinâmicas com as professoras, ");
			System.out.println("seguido das aulas extra classe e das atividades pedagógicas planejadas para o dia.");
			System.out.println("Às 9h as crianças lancham e depois dessa etapa são oferecidas outras atividades pedagógicas planejadas.");
			System.out.println("Às 10:30h temos o momento do banho e às 11h,");
			System.out.println("pontualmente é oferecido almoço.");
			System.out.println("");
			System.out.println("Logo em seguida, escovação e soneca.");
			System.out.println("Às 13h as crianças de Jardim I e II são acordadas para o reforço escolar e as demais,");
			System.out.println("a medida que acordam, seguem para a sala de atividades com a professora do integral");
			System.out.println("para que às 15h recebam o lanche.");
			System.out.println(" Após o lanche recebem atividades de artes, livros, brinquedos e depois é hora das trocas e higiene");
			System.out.println("Às 16:20h oferecemos um caldinho para as crianças que aceitam.");
			System.out.println("");
			System.out.println("0 = Opções iniciais");
			System.out.println("9 = Voltar");
			ficarOuN2 = in.nextLine();
			if (ficarOuN2.equals("0")) {atendimentoMain();}
			else if (ficarOuN2.equals("9")) {atendimentoOp2p3();}
			}
		else if (atendimentoOp2p3op.equals("4")) {
			System.out.println("");
			System.out.println("MATERIAL DIDÁTICO");
			System.out.println("A lista de materiais fica disponível desde o momento da visita,");
			System.out.println("no mural da escola e é entregue aos pais junto com o kit de matrícula.");
			System.out.println("Ela contempla só os materiais necessários ao planejamento do ano letivo,");
			System.out.println("sem excessos, porém, cada responsável ");
			System.out.println("fica incumbido de pesquisar pra adquirir pelos preços e condições adequadas à família.");
			System.out.println("");
			System.out.println("Na escola vendemos os livros e alguns itens exclusivos e personalizados:");
			System.out.println("Farda, nécessaire básica (para os itens de escovação + lençol colchonete com elástico) e camisetão de artes.\n");
			System.out.println("Maternal I - Coleção Mais Cores - Ed. Positivo - R$ 330,00");
			System.out.println("Maternal II, Jardim I e II - Coleções Conquista - Ed. Positivo - R$ 380,00\n");
			System.out.println("0 = Opções iniciais");
			System.out.println("9 = Voltar");
			ficarOuN3 = in.nextLine();
			if (ficarOuN3.equals("0")) {atendimentoMain();}
			else if (ficarOuN3.equals("9")) {atendimentoOp2p3();}
			}
		}
/////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp3() {
		String atendimentoOp3p, ficarSN, visitaSNs, visitaSNs2;
		Scanner in = new Scanner(System.in);
		System.out.println("");
		System.out.println("Para continuarmos, digite o NÚMERO da opção deseja e clique ENVIAR.");
		System.out.println("1 = Quero agendar uma visita !");
		System.out.println("2 = Documentos para a Matrícula !");
		System.out.println("3 = Desejo atendimento presencial para tirar mais dúvidas.");
		System.out.println("");
		System.out.println("0 = Opções iniciais");
		System.out.println("9 = Voltar");
		atendimentoOp3p = in.nextLine();
		if (atendimentoOp3p.equals("0")) {atendimentoMain();}
		else if (atendimentoOp3p.equals("9")) {atendimentoMain();}
		else if (atendimentoOp3p.equals("1")) {
			System.out.println("Atendemos somente com agendamentos. O dia deve ser escolhido com antecedência.");
			System.out.println("O horário será sempre às 17h.");
			System.out.println("Serão recebidos somente dois adultos por família.");
			System.out.println("Não é necessário chagar antes do horário. Teremos muito prazer em atendê-los.");
			System.out.println("Você será redirecionado para nossa Secretaria");
			System.out.println("Aguarde a chamada de um dos nossos atendentes");
			System.out.println("");
			System.out.println("Clique e confirme para continuar o atendimento");
			System.out.println("1 = Deseja continuar no Whatsapp");
			System.out.println("2 = Fazer uma ligação");
			System.out.println("");
			System.out.println("0 = Voltar ao inicio");
			System.out.println("9 = Voltar");
			visitaSNs = in.nextLine();
			if (visitaSNs.equals("0")) {atendimentoMain();}
			else if (visitaSNs.equals("9")) {atendimentoOp3();}
			else if (visitaSNs.equals("1")) {
				System.out.println("Aguarde e logo lhe retornaremos");}
			else if (visitaSNs.equals("2")) {
				System.out.println("");
				System.out.println("Encaminhando chamada");
				System.out.println("Aguarde...");}
			}
			else if (atendimentoOp3p.equals("3")) {
				System.out.println("Você está sendo redirecionado para a Secretaria");
				System.out.println("1 = Deseja continuar no Whatsapp");
				System.out.println("2 = Fazer uma ligação");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				visitaSNs2 = in.nextLine();
				if (visitaSNs2.equals("0")) {atendimentoMain();}
				else if (visitaSNs2.equals("9")) {atendimentoOp3();}
				else if (visitaSNs2.equals("1")) {
					System.out.println("Aguarde e logo lhe retornaremos");}
				else if (visitaSNs2.equals("2")) {
					System.out.println("");
					System.out.println("Encaminhando chamada");
					System.out.println("Aguarde...");}}
			else if (atendimentoOp3p.equals("2")) {
				System.out.println("Já fiz a visita e quero agendar a matrícula da minha criança");
				System.out.println("Documentos para a Matrícula:");
				System.out.println("");
				System.out.println("2 fotos, cópias, certidão de nascimento, cartão de vacina, comprovante de residência,");
				System.out.println("RG e CPF dos pais, RG e CPF + comprovante de residência do responsável ");
				System.out.println("financeiro (caso este não seja o pai ou a mãe da criança)");
				System.out.println("");
				System.out.println("O kit de matrícula é composto de Contrato, Ficha de Matrícula, Ficha Ambulatorial ");
				System.out.println("e Termo de Compromisso. Todos devem ser assinados pelo responsável financeiro, no ato da matrícula.");
				System.out.println("Não é permitido levar documentos de matrícula para assinatura fora da escola.");
				System.out.println("Normalmente o processo demora 30 minutos, quando as cópias dos documentos estão todas em mãos.");
				System.out.println("O pagamento da Parcela 1 é feito no ato em espécie ou PIX.");
				System.out.println("Não trabalhamos com cartão de crédito");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarSN = in.nextLine();
				if (ficarSN.equals("0")) {atendimentoMain();}
				else if (ficarSN.equals("9")) {atendimentoOp3();}
				}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp4() {
		String atendimentoOp4p, ficarAqui, ficarAqui2, ficarAqui3, ficarAqui4, ficarAqui5;
		Scanner in = new Scanner(System.in);
		 System.out.println("");
			System.out.println("Para continuarmos, digite o NÚMERO da opção deseja e clique ENVIAR.");
			System.out.println("1 = O que as crianças estudam na Educação Infantil ?");
			System.out.println("2 = Quais são os objetivos gerais da Educação Infantil ?");
			System.out.println("3 = Como é o dia da criança na creche");
			System.out.println("4 = Quais materiais compõem a lista de materiais escolares e como são utilizados?");
			System.out.println("5 = Existe período de teste ou adaptação na RENNOVARI?");
			System.out.println("");
			System.out.println("0 = Opções iniciais");
			atendimentoOp4p = in.nextLine();
			if (atendimentoOp4p.equals("0")) {atendimentoMain();}
			else if (atendimentoOp4p.equals("1")) {
				System.out.println("Na Educação Infantil, as crianças tem CONTEÚDOS ESPECÍFICOS ");
				System.out.println("como eixos estruturantes para o desenvolvimento da criança. São eles:");
				System.out.println("Movimento, Artes Visuais, Linguagem Oral e Escrita, Natureza e Sociedade, Matemática.");
				System.out.println("As orientações didáticas para a Educação Infantil são:  Educar e Cuidar");
				System.out.println("Todas as atividades na Educação Infantil são conduzidas pelas professoras mesmo. ");
				System.out.println("São elas:");
				System.out.println("Informática infantil, Ed. Ambiental, Ed. Nutricional, Inglês,");
				System.out.println("Psicomotricidade");
				System.out.println("Recreação no Quintal e no Parque Coberto");
				System.out.println("Musicalização");
				System.out.println("Libras entre outras");
				System.out.println("");
				System.out.println("Mais detalhes sobre rotina e método pedagógico são");
				System.out.println("passados na visita guiada às dependências da creche.");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarAqui = in.nextLine();
				if (ficarAqui.equals("0")) {atendimentoMain();}
				else if (ficarAqui.equals("9")) {atendimentoOp4();}
				}
			else if (atendimentoOp4p.equals("2")) {
				System.out.println("Quais são os objetivos gerais da Educação Infantil?");
				System.out.println("");
				System.out.println("Segundo o Referencial Curricular Nacional os objetivos são:");
				System.out.println("Desenvolver uma imagem positiva de si, atuando de forma cada vez mais independente,");
				System.out.println("com confiança em suas capacidades e percepção de suas limitações.");
				System.out.println("Descobrir e conhecer progressivamente seu próprio corpo, suas potencialidades ");
				System.out.println("e seus limites, desenvolvendo e valorizando hábitos de cuidado com a própria saúde e bem-estar.");
				System.out.println("");
				System.out.println("Estabelecer vínculos afetivos e de troca com adultos e crianças, ");
				System.out.println("fortalecendo sua autoestima e ampliando gradativamente suas possibilidades de comunicação e interação social.");
				System.out.println("Estabelecer e ampliar cada vez mais as relações sociais,");
				System.out.println("aprendendo aos poucos a articular seus interesses e pontos de vista com os demais");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarAqui2 = in.nextLine();
				if (ficarAqui2.equals("0")) {atendimentoMain();}
				else if (ficarAqui2.equals("9")) {atendimentoOp4();}
			}
			else if (atendimentoOp4p.equals("3")) {
				System.out.println("Como é o dia da criança na creche?");
				System.out.println("");
				System.out.println("ROTINAS");
				System.out.println(" A partir das 7h nossas crianças chegam e são acolhidas. Às 7:30h temos a roda de conversa com música e dinâmicas com as professoras, ");
				System.out.println("seguido das aulas extra classe e das atividades pedagógicas planejadas para o dia.");
				System.out.println("Às 9h as crianças lancham e depois dessa etapa são oferecidas outras atividades pedagógicas planejadas.");
				System.out.println("Às 10:30h temos o momento do banho e às 11h,");
				System.out.println("pontualmente é oferecido almoço.");
				System.out.println("");
				System.out.println("Logo em seguida, escovação e soneca.");
				System.out.println("Às 13h as crianças de Jardim I e II são acordadas para o reforço escolar e as demais,");
				System.out.println("a medida que acordam, seguem para a sala de atividades com a professora do integral");
				System.out.println("para que às 15h recebam o lanche.");
				System.out.println(" Após o lanche recebem atividades de artes, livros, brinquedos e depois é hora das trocas e higiene");
				System.out.println("Às 16:20h oferecemos um caldinho para as crianças que aceitam.");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarAqui3 = in.nextLine();
				if (ficarAqui3.equals("0")) {atendimentoMain();}
				else if (ficarAqui3.equals("9")) {atendimentoOp4();}
			}
			else if (atendimentoOp4p.equals("4")) {
				System.out.println("Quais materiais compõem a lista de materiais escolares e como são utilizados?");
				System.out.println("");
				System.out.println("MATERIAL DIDÁTICO");
				System.out.println("A lista de materiais fica disponível desde o momento da visita,");
				System.out.println("no mural da escola e é entregue aos pais junto com o kit de matrícula.");
				System.out.println("Ela contempla só os materiais necessários ao planejamento do ano letivo,");
				System.out.println("sem excessos, porém, cada responsável ");
				System.out.println("fica incumbido de pesquisar pra adquirir pelos preços e condições adequadas à família.");
				System.out.println("");
				System.out.println("Na escola vendemos os livros e alguns itens exclusivos e personalizados:");
				System.out.println("Farda, nécessaire básica (para os itens de escovação + lençol colchonete com elástico) e camisetão de artes.\n");
				System.out.println("Maternal I - Coleção Mais Cores - Ed. Positivo - R$ 330,00");
				System.out.println("Maternal II, Jardim I e II - Coleções Conquista - Ed. Positivo - R$ 380,00\n");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarAqui4 = in.nextLine();
				if (ficarAqui4.equals("0")) {atendimentoMain();}
				else if (ficarAqui4.equals("9")) {atendimentoOp4();}
			}
			else if (atendimentoOp4p.equals("5")) {
				System.out.println("");
				System.out.println("Existe período de teste ou adaptação na RENNOVARI?");
				System.out.println("O que a nossa prática e os teóricos da educação afirmam é que a adaptação,");
				System.out.println("assim como o desenvolvimento das crianças,");
				System.out.println("é diferente para cada indivíduo. Algumas crianças manifestam ");
				System.out.println("muito choro inicialmente, enquanto outras não choram no início,");
				System.out.println("manifestando mais tarde essa reação");
				System.out.println("Algumas ficam muito desconfiadas no começo,");
				System.out.println("enquanto outras parece que já nasceram em nosso meio.");
				System.out.println("O que é certo, no entanto, é que todas as crianças,");
				System.out.println("se bem acolhidas, se adaptam.");
				System.out.println("Essa fase pode durar semanas ou até meses, a depender de cada criança ");
				System.out.println("se bem acolhidas, se adaptam.");
				System.out.println("o que pode favorecer ou atrapalhar e muito na aceitação da criança ao novo ambiente e os novos adultos e crianças.");
				System.out.println("A nossa certeza não muda: toda criança é capaz de se adaptar ao ambiente escolar,");
				System.out.println("por isso não recebemos alunos sem contrato ou para um período para adaptação a título de teste.");
				System.out.println("");
				System.out.println("0 = Opções iniciais");
				System.out.println("9 = Voltar");
				ficarAqui5 = in.nextLine();
				if (ficarAqui5.equals("0")) {atendimentoMain();}
				else if (ficarAqui5.equals("9")) {atendimentoOp4();}
			}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoMain() {
		String atendimento1;
		Scanner in = new Scanner(System.in);
		System.out.println("Nosso horário de atendimento é de Seg - Sex : 07:30h - 17:15h");
		System.out.println("");
		System.out.println("Sou Larinha, o BOT da RENNOVARI e vou realizar o seu atendimento.");
		System.out.println("");
		System.out.println("Vamos começar! ");
		System.out.println("Digite uma das opções e clique para "+"Enviar"+" !");
		System.out.println("1 = Já sou cliente RENNOVARI");
		System.out.println("2 = Quero conhecer a RENNOVARI");
		System.out.println("3 = Quero fazer um agendamento");
		System.out.println("4 = Duvidas frequentes");
		System.out.println("5 = Nossa localização e Redes Sociais");
		System.out.println("");
		atendimento1 = in.nextLine();
		if (atendimento1.equals("1")) {atendimentoOp1();}
		else if (atendimento1.equals("2")) {atendimentoOp2();}
		else if (atendimento1.equals("3")) {atendimentoOp3();}
		else if (atendimento1.equals("4")) {atendimentoOp4();}
		else if (atendimento1.equals("5")) {atendimentoOp5();}
		else if (atendimento1.equals("")) {resposta1invalida();atendimentoMain();}
		else {resposta1invalida();atendimentoMain();}
		}
//////////////////////////////////////////////////////////////////////////////////////////////////
	static void atendimentoOp5() {
		Scanner in = new Scanner(System.in);
		String seila;
		System.out.println("");
		 System.out.println("Nossa Localização e Redes Sociais");
		 System.out.println("linktr.ee/rennovari");
		 System.out.println("");
		 System.out.println("0 = Opções iniciais");
		 seila = in.nextLine();
		 if (seila.equals("0")) {atendimentoMain();}
		 else if (seila.equals("")) {atendimentoOp5();}
	}
//////////////////////////////////////////////////////////////////////////////////////////////////
	public static void main(String[] args) {
		nomeINFO();
		atendimentoMain();
		}
	}
