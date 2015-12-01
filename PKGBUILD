_langs=(afr amh ara asm aze_cyrl aze bel ben bod bos bul cat ceb ces chi_sim chi_tra chr cym dan_frak dan deu_frak deu dzo ell eng enm epo equ est eus fas fin fra frk frm gle glg grc guj hat heb hin hrv hun iku ind isl ita_old ita jav jpn kan kat_old kat kaz khm kir kor kur lao lat lav lit mal mar mkd mlt msa mya nep nld nor ori osd pan pol por pus ron rus san sin slk_frak slk slv spa_old spa sqi srp_latn srp swa swe syr tam tel tgk tgl tha tir tur uig ukr urd uzb_cyrl uzb vie yid)

pkgbase=tesseract-data
pkgname=($(for l in ${_langs[@]}; do echo tesseract-data-${l}; done))
pkgver=3.04.00
pkgrel=1
pkgdesc="Trained language data for tesseract OCR Engine"
arch=('x86_64')
url="https://github.com/tesseract-ocr/tessdata"
license=('Apache 2.0')
depends=('tesseract-ocr=3.04.00')
groups=('tesseract' 'tesseract-data' 'localization')
source=("tessdata::https://github.com/tesseract-ocr/tessdata/archive/${pkgver}.tar.gz")
sha512sums=('4fbb66137c729e16c7a9e35b09916a45c1bb5ec5a7002a22647e0b10975362cb44c6d6c0c997baf25866f78749ec2d4a86317ec3fb664bd963243e230516d162')

for l in ${_langs[@]}; do
        eval "
package_tesseract-data-${l}(){
        provides=('tesseract-data-${l}')
        conflicts=('tesseract-data-${l}')

        cd \"\$srcdir/tessdata-${pkgver}\"
        mkdir -p \"\$pkgdir/usr/share/tessdata\"
        cp ${l}.* \"\$pkgdir/usr/share/tessdata/\"
        find \$pkgdir/usr/share/tessdata -type f -exec chmod 0644 {} \;
}
"
done
