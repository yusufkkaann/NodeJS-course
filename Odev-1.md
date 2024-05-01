1:Hepimizin Matematik derslerinden bildiği üzere Dairenin Alanı = π x r2 şeklinde hesaplanır.
Node.JS Javascript çalışma ortamında yarıçap değerini konsoldan parametre olarak girerek alanı bulmaya çalışacağız. 
Konsol çıktısı: Yarıçapı (Yarıçap) olan dairenin alanı: (Alan) şeklinde olmalıdır.

----------------------------------------------------------------------------
const arguments = process.argv.slice(2);
//console.log("parse işlemi", parseInt(arguments[0]));
function alanHesap(r) {
  let alan = Math.PI * r * r;
  alan = alan.toFixed(2);
  return alan;
}
console.log(
  `Yarıçapı ${arguments[0]} olan dairenin alanı: ${alanHesap(
    parseInt(arguments[0])
  )}`
);
----------------------------------------------------------------------------
