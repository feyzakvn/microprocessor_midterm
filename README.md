#start=emulation Kit.exe#


#make_bin#

ayrac db ?  
dakika db ? 
dakika_goster db ?  
saat db ?  
saat_goster db ?
saniye db ?
saniye_goster db ?






mov al, bl
shr al, 4
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov ayrac, al

; Dakika g�stergeye yazd�r
mov bl, dakika
mov al, bl
and al, 0fh
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov dakika_goster, al

mov al, bl
shr al, 4
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov ayrac, al

; Saat g�stergeye yazd�r
mov bl, saat
mov al, bl
and al, 0fh
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov saat_goster, al

mov al, bl
shr al, 4
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov ayrac, al

; Saniye g�stergeye yazd�r
mov bl, saniye
mov al, bl
and al, 0fh
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov saniye_goster, al

mov al, bl
shr al, 4
mov bl, al ; al de�erini ge�ici olarak bl'ye kopyala
mov al, rakam_tablosu[bx] ; bl i�indeki de�eri kullanarak bellek adresine eri�

mov ayrac, al

; G�stergeyi ��k�� portlar�na yazd�r
mov ah, 0bh
mov bh, 00h
mov bl, saat_goster
mov dx, 2030h
int 21h

mov bl, dakika_goster
mov dx, 2032h
int 21h

mov bl, saniye_goster
mov dx, 2034h
int 21h

mov bl, ayrac
mov dx, 2036h
int 21h

; Bekleme
mov cx, 5000





rakam_tablosu db 3fh, 06h, 5bh, 4fh, 66h, 6dh, 7dh,07h,07fh,06fh





