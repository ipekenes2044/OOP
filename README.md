class Personel:
    mesai = "9 - 18"
    şirket = "Pythonla Güzel Günler"

    def __init__(self, isim, maaş,yetenekler,konum):
        print("Yeni bir personel oluşturuldu. İsmi:", isim)
        self.isim = isim
        self.yetenekler = yetenekler if yetenekler is not None else []
        self.maaş = maaş
        self.konum = konum
        self.günsayısı = 0


    def çalış(self):
        self.günsayısı += 1
        print(self.isim, "şu anda çalışıyor. Toplam gün sayısı:", self.günsayısı)

    def terfi(self):
        self.maaş += 200
        print("Tebrikler!", self.isim, "terfi aldı! Yeni maaşı:", self.maaş)

    def bilgileriGöster(self):
        print("*" * 15)
        print("Personelin ismi:", self.isim)
        print("Personelin konumu:", self.konum)
        print("Personelin yetenekleri:", self.yetenekler)
        print("Personelin maaşı:", self.maaş)
        print("Personelin toplam gün sayısı:", self.günsayısı)
        print("*" * 15)



class Yönetici(Personel):

    def __init__(self,isim,maaş,yetenekler,konum,yönetimbecerisi):
        super().__init__(isim,maaş,yetenekler,konum)
        self.yönetimbecerisi = yönetimbecerisi

    def terfi(self):
        print("Tebrikler!", self.isim, "terfi aldı! Yeni maaşı ise şu oldu: ", self.maaş + 500)
        self.maaş += 500
    def gezinti(self):
        print(self.isim, "adlı yönetici şu anda şube gezisine çıktı")

    def bilgileriGöster(self):
        super().bilgileriGöster()
        print("Yöneticinin yönetim becerisi:",self.yönetimbecerisi)
        print("*"*15)
    def çalış(self):
        super().çalış()
        self.yönetimbecerisi += 0.5
        print("Mevcut yönetim becerisi:",self.yönetimbecerisi)

mustafa = Yönetici("Mustafa", 2000, ["iyi yönetir"],"Yönetici",30)
ahmet = Personel("Ahmet",1600,["Python kullanır"], "Normal Personel")
mustafa.çalış()
mustafa.çalış()
mustafa.çalış()
mustafa.çalış()

