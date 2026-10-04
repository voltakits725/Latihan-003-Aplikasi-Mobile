# LAUNDRY EXPRESS TAPI GA EXPRESS

**RAFLY KURNIAWAN - 1124160165**

## BUSINESS RULE

- **BR-01:** Tarif laundry sebesar Rp7.000 untuk setiap kg.
- **BR-02:** Berat laundry di bawah 2 kg tetap dihitung 2 kg.
- **BR-03:** Layanan Express mendapat tambahan biaya 50%.

## SOURCE CODE

```dart
void main(){
  double totalBerat = 2;
  bool express = false;

  double beratPakaian = hitungBeratPakaian(totalBerat);
  double biayaLaundry = hitungBiayaLaundry(beratPakaian);
  double totalBiaya = hitungTotalBiayaLaundry(biayaLaundry, express);

  print("=== ORANG KE LAUNDRY = ORANG YANG MALAS NYUCI ===");
  print("Berat Pakaian : $beratPakaian kg");
  print("Biaya Laundry : Rp$biayaLaundry");
  print("Express       : $express");
  print("Total Bayar   : Rp$totalBiaya");
}

double hitungBeratPakaian(double beratPakaian){
  if(beratPakaian < 2){
    return 2;
  }else{
    return beratPakaian;
  }

}

double hitungBiayaLaundry(double beratPakaian){
  const double BIAYALAUNDRY = 7000;
  
  double biayaLaundry = beratPakaian * BIAYALAUNDRY;

  return biayaLaundry;

}

double hitungTotalBiayaLaundry(double biayaLaundry, bool express){
  const double EXPRESS = 0.5;
  if (express){
    double biayaExpress = biayaLaundry * EXPRESS;
    double total = biayaLaundry + biayaExpress;
    return total;
  }else{
    return biayaLaundry;
  }
}