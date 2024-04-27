# web_tasarimi_bilmemka-
from flask import Flask
import random

app = Flask(__name__)

liste = [
    "Elon Musk, sosyal ağların içeriği görüntülemek için mümkün olduğunca fazla zaman harcamamız için bizi platformun içinde tutmak üzere tasarlandığını iddia ediyor.",
    "Teknolojik bağımlılıkla mücadele etmenin bir yolu, zevk veren ve ruh halini iyileştiren faaliyetler aramaktır.",
    "Elon Musk ayrıca sosyal ağların düzenlenmesini ve kullanıcıların kişisel verilerinin korunmasını savunmaktadır. Sosyal ağların hakkımızda büyük miktarda bilgi topladığını ve bu bilgilerin daha sonra düşüncelerimizi ve davranışlarımızı manipüle etmek için kullanılabileceğini iddia ediyor.",
    "Sosyal ağların olumlu ve olumsuz yanları vardır ve bu platformları kullanırken her ikisinin de farkında olmalıyız.",
]

odev = ["yazı", "tura"]

@app.route("/")
def home():
    return "<a href='/teknoloji'>Rastgele bir gerçeği görüntüle!</a><br><a href='/yazitura'>Yazı mı Tura mı?</a>"

@app.route("/teknoloji")
def teknoloji():
    rastgele_kelime = random.choice(liste)
    return f'<h1>{rastgele_kelime}</h1>'

@app.route("/yazitura")
def yazitura():
    rastgele_sekme = random.choice(odev)
    return f'<h1>{rastgele_sekme}</h1>'


app.run(debug=True)
