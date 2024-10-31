async function enviarScript(scriptText){
	const lines = scriptText.split(/[\n\t]+/).map(line => line.trim()).filter(line => line);
	main = document.querySelector("#main"),
	textarea = main.querySelector(`div[contenteditable="true"]`)
	
	if(!textarea) throw new Error("Não há uma conversa aberta")
	
	for(const line of lines){
		console.log(line)
	
		textarea.focus();
		document.execCommand('insertText', false, line);
		textarea.dispatchEvent(new Event('change', {bubbles: true}));
	
		setTimeout(() => {
			(main.querySelector(`[data-testid="send"]`) || main.querySelector(`[data-icon="send"]`)).click();
		}, 100);
		
		if(lines.indexOf(line) !== lines.length - 1) await new Promise(resolve => setTimeout(resolve, 250));
	}
	
	return lines.length;
}

enviarScript(`
Calaboca garota sua loka
feia
rechonchuda
filhotinho de thais carla
moto moto
gorda
157 geladeira
botijão de gás
galão de agua
piscina de mil litros
bola da copa do mundo
duas volta na balança
mobdick
chupeta de baleia cabeçuda
cabeça de nois todos
cabeça de martelo
gabeça prenha
cabeça gravida
garota olha o tamanho da sua testa
garota, se meu vô ver vc na rua ele passa o fação de mata peixe na sua lata
tlgd aquele facão de mate bagre de 10 kilo?
tua testa é tão grande que dá pra forjar uma katana nela
gravidez psicologica
tu parece aqueles pirulito pop de 1,50
tlgd garota, tu parece o et daquele filme et tlgd
só que tu não ia dar 3 pedalada na bike q pq tu ia cair no chão com o peso dessa jabulani 2014 que tu chama de cabeça
tlgd garota, tu ia dar com a tua cabeça numa quina de calçada ia ficar igual a rainha de copas da alice no pais das maravilhas
tu passa tanto reboco na tua cara que tu ta parecendo o chapeleiro tlgd?
falando em pais das maravilhas tu passa o chapeleiro
vai arrumar esse teu cabelo garota
ta parecendo o felca com esse cabelo
vai raspar esse teu suvaco garota
ta parecendo a amazonia esse pelo no teu braço
teu suvaco tem tanto cabelo
que parece o michael jackson tlgd
um lado desse teu suvaco parece o michael jackson e o outro parece o bruno mars
tlgd garota
vai raspar esse bigode de orochinho ai garota
tu parece o proprio satanas garota
isso se tu não for né
com esse zoião revirado
tua mãe apareceu com vc em casa garota
teu pai foi comprar cigarro e leite micilon e tudo q tu pode imaginar
tlgd garota
fica idolatrando japones boyola q sobe no palco pra ficar gemendo garota
agr teu pai ta vendendo ovo garota
todo dia ele passa aqui na rua gritando o carro do ovo passando na sua rua.
