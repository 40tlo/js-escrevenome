//variáveis da bolinha let xBolinha = 100; let yBolinha = 200; let diametro = 22; let raio = diametro / 2;

//velocidade da bolinha let velocidadeXBolinha = 6; let velocidadeYBolinha = 6;

//variáveis da raquete let xRaquete = 5; let yRaquete = 150; let raqueteComprimento = 10; let raqueteAltura = 90;

//variáveis do oponente let xRaqueteOponente = 585; let yRaqueteOponente = 150; let velocidadeYOponente;

let colidiu = false;

//placar do jogo let meusPontos = 0; let pontosDoOponente = 0;

function setup() { createCanvas(600, 400); }

function draw() { background(0); mostraBolinha(); movimentaBolinha(); verificaColisaoBorda(); mostraRaquete(xRaquete, yRaquete); mostraRaquete(xRaqueteOponente, yRaqueteOponente); movimentaMinhaRaquete(); // verificaColisaoRaquete(); verificaColisaoRaquete(xRaquete, yRaquete); verificaColisaoRaquete(xRaqueteOponente, yRaqueteOponente); movimentaRaqueteOponente(); incluiPlacar(); marcaPonto(); }

function mostraBolinha() { circle(xBolinha, yBolinha, diametro); }

function movimentaBolinha() { xBolinha += velocidadeXBolinha; yBolinha += velocidadeYBolinha; }

function verificaColisaoBorda() { if (xBolinha + raio > width || xBolinha - raio < 0) { velocidadeXBolinha *= -1; } if (yBolinha + raio > height || yBolinha - raio < 0) { velocidadeYBolinha *= -1; } }

function mostraRaquete(x,y) { rect(x, y, raqueteComprimento, raqueteAltura); }

function movimentaMinhaRaquete() { if(keyIsDown(UP_ARROW)) { yRaquete -= 10; } if(keyIsDown(DOWN_ARROW)) { yRaquete += 10; } }

function verificaColisaoRaquete() { if (xBolinha - raio < xRaquete + raqueteComprimento && yBolinha - raio < yRaquete + raqueteAltura && yBolinha + raio > yRaquete) { velocidadeXBolinha *= -1; } }

function verificaColisaoRaquete(x,y) { colidiu = collideRectCircle(x, y, raqueteComprimento, raqueteAltura, xBolinha, yBolinha, raio); if(colidiu) { velocidadeXBolinha *= -1; } }

function movimentaRaqueteOponente() { velocidadeYOponente = yBolinha - yRaqueteOponente - raqueteComprimento / 2 - 30; yRaqueteOponente += velocidadeYOponente; }

function incluiPlacar() { fill(255); text(meusPontos, 278, 26); text(pontosDoOponente, 321, 26); }

function marcaPonto() { if (xBolinha > 590) { meusPontos += 1; } } }

Este trabalho está licenciado sob CC BY-NC-SA 4.0
<p xmlns:cc="http://creativecommons.org/ns#" >Este trabalho está licenciado sob <a href="https://creativecommons.org/licenses/by-nc-nd/4.0/?ref= selector-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-ND 4.0<img style="height:22px!important;margin-left:3px ;alinhamento vertical:fundo do texto;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical -align:texto inferior;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical -align:texto inferior;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical -align:texto inferior;" src="https://mirrors.creativecommons.org/presskit/icons/nd.svg?ref=chooser-v1" alt=""></a></p>
