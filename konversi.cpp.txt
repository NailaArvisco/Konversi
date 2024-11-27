#include <iostream>
#include <iomanip> 
#include <limits>
#include <string>


using namespace std;



double convertCurrency(double amount, double exchangeRate) {
    return amount * exchangeRate;
}

int main() {
    double amount;
    double result; 
    int uang;    
    const double USD_TO_IDR = 15000.0; 
    const double USD_TO_EUR = 0.94;    
    const double EUR_TO_IDR = 16000.0; 
    const double EUR_TO_USD = 1.06;  
    const double IDR_TO_EUR = 0.00005989;
    const double IDR_TO_USD = 0.000063;

    
       
    cout << "-----Program Konversi Mata Uang Kelompok 7 Slebew-----\n";

    while (true)
    {
      cout << "Pilih Mata Uang yang Akan Dikonversi:\n";
      cout << "1. USD ke IDR\n";
      cout << "2. USD ke EUR\n";
      cout << "3. EUR ke IDR\n";
      cout << "4. EUR ke USD\n";
      cout << "5. IDR ke EUR\n";
      cout << "6. IDR ke USD\n";
      cout << "7. Keluar\n";
      cout << "Masukkan pilihan 1-7: ";
      cin >> uang;

      while (cin.fail() || uang < 1 || uang > 7) {
         cin.clear(); 
         cin.ignore(numeric_limits<streamsize>::max(), '\n'); 
         cout << "Pilihan tidak valid. Silakan coba lagi: ";
         cin >> uang;
        }
      

       if (uang == 7) {
            cout << "Keluar dari sistem...\n";
           break;  
        }

      cout << "Masukkan jumlah uang yang ingin dikonversi: ";
      cin >> amount;

      while (cin.fail() || amount < 0) {
          cin.clear();
          cin.ignore(numeric_limits<streamsize>::max(), '\n');
          cout << "Jumlah uang tidak valid. Silakan coba lagi: ";
          cin >> amount;
        }
    
      cout << fixed << setprecision(2);  
        switch (uang) {
            case 1: 
                cout << amount << " USD = " << convertCurrency(amount, USD_TO_IDR) << " IDR\n";
                break;
            case 2: 
                cout << amount << " USD = " << convertCurrency(amount, USD_TO_EUR) << " EUR\n";
                break;
            case 3: 
                cout << amount << " EUR = " << convertCurrency(amount, EUR_TO_IDR) << " IDR\n";
                break;
            case 4: 
                cout << amount << " EUR = " << convertCurrency(amount, EUR_TO_USD) << " USD\n";
                break;
            case 5: 
                cout << amount << " IDR = " << convertCurrency(amount, IDR_TO_EUR) << " USD\n";
                break;
            case 6: 
                cout << amount << " IDR = " << convertCurrency(amount, IDR_TO_USD) << " USD\n";
                break;
            default:
                cout << "Pilihan tidak valid. Silakan coba lagi.";

        }
    
    } 
    


    return 0;
}