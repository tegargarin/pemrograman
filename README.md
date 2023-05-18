#define _CRT_SECURE_NO_WARNINGS
#include <iostream>
#include <conio.h>
#include <ctime>
#include<windows.h>
#include<fstream>


using namespace std;
int c, d, e, f, g, h;
int stokmakan[10];
string menu[10] = { "Rendang Sapi","Gulai Kambing","Ayam {Goreng/Bakar)","Telur Balado","Telur Dadar Padang","Teri Terong Cabai Hijau","Perkedel Kentang","Daun Singkong Rebus","Teh(Es/Hangat)","jeruk(Es/Hangat)" };
int total[100];
int cuan[1] = {0} ;
int pass();
int admiin();
int jual();
int stok();
int lihat();
void waktu();
int direktuur();

int main()
{
	pass();
	cin.get();
	return 0;
}

int pass()
{
awal:
if1:
	string username;
	int password = 0;
	int i;
	cout << "------------------------------------------\n";
	cout << "         RUMAH MAKAN MENTARI PAGI         \n";
	cout << "------------------------------------------\n\n";
	string admin = "mentari";
	string direktur = "pakjoko";
	int pass = 123456;
	int passdir = 311213;
	int login = 0;
	i = 0;

	cout << "1.Login Sebagai admin " << endl;
	cout << "2.Login Sebagai Direktur    " << endl;
	cout << "Pilih : "; cin >> i;

	if (i == 1)
	{


		cout << "username : "; cin >> username;
		cout << "password : "; cin >> password;
		if (username == admin && password == pass)
		{
			i = 4;
			login = 1;
			cout << "\n--------------------\n";
			cout << "  Login Sebagai Admin   " << endl;
			cout << "--------------------\n";
			cout << "klik ENTER untuk melanjutkan";
			cin.get();
			cin.get();
			system("cls");
			admiin();
		}
		else
		{
			cout << "\n--------------------\n";
			cout << "  password salah   " << endl;
			cout << "--------------------\n";
			cout << "klik ENTER untuk melanjutkan";
			cin.get();
			cin.get();
			system("cls");
			goto if1;


		}
	}
	else if (i == 2)
	{
		cout << "username : "; cin >> username;
		cout << "password : "; cin >> password;
		if (username == direktur && password == passdir)
		{
			i = 4;
			login = 1;
			cout << "\n--------------------\n";
			cout << "  Login Sebagai Direktur   " << endl;
			cout << "--------------------\n";
			cout << "klik ENTER untuk melanjutkan";
			cin.get();
			cin.get();
			system("cls");
			direktuur();

		}
		else
		{
			cout << "\n--------------------\n";
			cout << "  password salah   " << endl;
			cout << "--------------------\n";
			cout << "klik ENTER untuk melanjutkan";
			cin.get();
			cin.get();
			system("cls");
			goto if1;


		}
	}
	else
	{
		cout << endl;
		cout << "pilihan tidak ada !!! " << endl;
		cout << "klik ENTER untuk melanjutkan";
		cin.get();
		cin.get();
		system("cls");
		goto awal;
	}

	cin.get();
	return 0;
}

int admiin()
{
awal:
	system("cls");
	int a = 0;
	cout << "pilih pekerjaan" << endl;
	cout << "1. jual" << endl;
	cout << "2. update stock" << endl;
	cout << "3. lihat stock" << endl;
	cout << "4. Log Out" << endl;
	cout << "pilihan : "; cin >> a;
	if (a == 1)
	{
		jual();
	}
	else if (a == 2)
	{
		stok();
	}
	else if (a == 3)
	{

		lihat();
	}
	else if (a == 4)
	{

		pass();
	}
	else {
		cout << "pilihan tidak ada";
		goto awal;
	}

	return 0;
}

int direktuur()
{
awal:

	int a = 0;
	cout << "1. penjualan hari ini" << endl;
	cout << "2. lihat stok yang masih tersisa " << endl;
	cout << "3. Log Out" << endl;
	cout << "pilih : ";
	cin >> a;
	cout << endl;
	if (a == 1)
	{
		cout << "Rp. " << cuan[0] << endl;
		cin.get();
		cin.get();
		char b;
		cout << "apakah ingin print hasil laporan ? <y/t> ";
			cin >> b;
		if (b == 'y' || b == 'Y')
		{

		}
		if (b == 't' || b == 'T')
		{
			direktuur();
		}
	}
	else if (a == 2)
	{
		lihat();
	}
	else {
		cout << "pilihan tidak ada";
		goto awal;
	}
	return 0;
}

int stok()
{
awal:
	system("cls");
	int a;
	cout << "===========================================" << endl;
	cout << "=           UPDATE STOK MAKANAN           =" << endl;
	cout << "=     SILAHKAN MASUKKAN PORSI HARI INI    =" << endl;
	cout << "===========================================" << endl;
	for (int i = 0; i < 10; i++)
	{
		cout << "Jumlah Dari " << menu[i] << " = ";
		cin >> stokmakan[i];
	}
	cout << "UPDATED!!" << endl;
pilih:
	cout << "menu   : 1" << endl;
	cout << "update : 2" << endl;
	cout << "pilih : "; cin >> a;
	if (a == 1)
	{
		admiin();
		system("cls");
	}
	else if (a == 2)
	{
		goto awal;
		system("cls");
	}
	else
	{
		cout << "pilihan tidak ada!!" << endl << endl;
		goto pilih;
	}
	return 0;

}

int lihat()
{
awal:
	char a;
	system("cls");
	cout << "=============================================" << endl;
	cout << "=              MENU LIST BARANG             =" << endl;
	cout << "=============================================" << endl;
	cout << "1." << menu[0] << " stock           : " << stokmakan[0] << endl;
	cout << "2." << menu[1] << " stock          : " << stokmakan[1] << endl;
	cout << "3." << menu[2] << " stock    : " << stokmakan[2] << endl;
	cout << "4." << menu[3] << " stock           : " << stokmakan[3] << endl;
	cout << "5." << menu[4] << " stock     : " << stokmakan[4] << endl;
	cout << "6." << menu[5] << " stock : " << stokmakan[5] << endl;
	cout << "7." << menu[6] << " stock       : " << stokmakan[6] << endl;
	cout << "8." << menu[7] << " stock    : " << stokmakan[7] << endl;
	cout << "9." << menu[8] << " stock        : " << stokmakan[8] << endl;
	cout << "10." << menu[9] << " stock      : " << stokmakan[9] << endl;

pilih:
	cout << "balik menu <y/t> : " << endl;
	cin >> a;
	if (a == 'y' || a == 'Y')
	{
		admiin();
		system("cls");
	}
	else if (a == 't' || a == 'T')
	{
		goto awal;
		system("cls");
	}
	else
	{
		cout << "pilihan tidak ada!!" << endl << endl;
		goto pilih;
	}
	return 0;
}

int jual()

{
awal:
	system("cls");
	char a;
	int i = 0;
	int j = 0;
	int porsi[100], sub_total[100], pilih[100], harga[100];
	string menu[100];
	int total_bayar = 0;
	int kembalian, tunai;
	bool selesai = false;
	cout << "------------------------------------------" << endl;
	cout << "DAFTAR MENU MAKANAN & MINUMAN MENTARI PAGI" << endl;
	cout << "1. Rendang SapI                Rp. 18000" << endl;
	cout << "2. Gulai Kambing               Rp. 15000" << endl;
	cout << "3. Ayam (Goreng/Bakar)         Rp. 12000" << endl;
	cout << "4. Telur Balado                Rp. 3500" << endl;
	cout << "5. Telur Dadar Padang          Rp. 3500" << endl;
	cout << "6. Teri Terong Cabai Hijau     Rp. 4000" << endl;
	cout << "7. Pekedel Kentang             Rp. 1500" << endl;
	cout << "8. Daun Singkong Rebus         Rp. 3000" << endl;
	cout << "9. Tea (Es/Hangat)             Rp. 2500" << endl;
	cout << "10. Jeruk (es/Hangat)          Rp. 3000" << endl;
	cout << "------------------------------------------" << endl;
	cout << "Tekan 0 jika selesai melakukan pemesanan" << endl << endl;
memilih:
	while (selesai == false)
	{
		cout << "menu yang akan dipilih : ";
		cin >> pilih[i];

		if (pilih[i] <= 10)
		{
			if (pilih[i] == 0)
			{
				selesai = true;
				goto akhir;
			}

			else {
				switch (pilih[i]) {
				case 1: menu[i] = "Rendang Sapi             "; harga[i] = 18000; break;
				case 2: menu[i] = "Gulai Kambing            "; harga[i] = 15000; break;
				case 3: menu[i] = "Telur Balado             "; harga[i] = 3500; break;
				case 4: menu[i] = "Ayam (Goreng/Bakar)      "; harga[i] = 12000; break;
				case 5: menu[i] = "Telur Dadar Padang       "; harga[i] = 3500; break;
				case 6: menu[i] = "Teri Terong Cabai Hijau  "; harga[i] = 4000; break;
				case 7: menu[i] = "Pekedel Kentang          "; harga[i] = 1500; break;
				case 8: menu[i] = "Daun Singkong Rebus      "; harga[i] = 3000; break;
				case 9: menu[i] = "Tea (Es/Hangat)          "; harga[i] = 2500; break;
				case 10: menu[i] = "Jeruk (es/Hangat)       "; harga[i] = 3000; break;
				default: menu[i] = ""; harga[i] = 0;
				}
			}
			cout << "Jumlah Porsi " << menu[i] << " : ";
			cin >> porsi[i];		cout << endl;
			//syarat apakah stokmasih tersedia atau tidak
			if (porsi[i] > stokmakan[i])
			{
				cout << "maaf porsi habis" << endl;
				cout << "silahkan memilih menu lain" << endl << endl;
				goto memilih;
			}
			else
			{
				stokmakan[i] = stokmakan[i] - porsi[i];//rumus untuk pengurangan stok makan
				sub_total[i] = porsi[i] * harga[i];
				total_bayar = total_bayar + sub_total[i];
				i++;
			}
		}
		else
		{
			cout << "menu tidak ada" << endl;
			goto memilih;
		}




	}
akhir:
	system("cls");
	cout << endl;
	cout << "         Pembelian Masakan Padang" << endl;
	cout << "----------------------------------------------------------------------" << endl;
	cout << "No	Nama Menu    	  	         Harga          Jumlah         Sub Total " << endl;
	cout << "----------------------------------------------------------------------" << endl;

	for (int a = 0; a < i; a++) {
		cout << a + 1 << "	" << menu[a] << "	" << harga[a] << "		" << porsi[a] << "		" << sub_total[a] << endl;
	}
	cout << "----------------------------------------------------------------------" << endl;
	cout << "Total Bayar     : Rp." << total_bayar << endl;
	cout << "Tunai           : Rp. "; cin >> tunai;
	//program untuk membandingkan harga dengan uang,jika kurang tidak bisa
	if (tunai < total_bayar)
	{
		char a;
		cout << "uang kurang ! " << endl;
	pilihan:

		cout << "lanjut pembayaran/tidak <y/t> : ";
		cin >> a;
		if (a == 'y' || a == 'Y')
		{

			goto akhir;
		}
		else if (a == 't' || a == 'T')
		{
			goto awal;
		}
		else {
			cout << "pilihan tidak ada" << endl;
			goto pilihan;
		}
	}
	//rumus perhitungan kembalian
	kembalian = tunai - total_bayar;
	cout << "Kembalian       : Rp. " << kembalian << endl;
	cout << "----------------------------------------------------------------------" << endl << endl;
	cuan[0] = cuan[0] + total_bayar;
	//program untuk struk pembelian
	ofstream myFile;
	myFile.open("StrukPembayaran.txt", ios::trunc);
	cout << " Mencetak Struk Pembayaran " << endl << endl;
	myFile << "=========================================================================================================" << endl;
	myFile << "                             R U M A H   M A K A N   M E N T A R I   P A G I                             " << endl;
	myFile << "=========================================================================================================" << endl << endl;
	myFile << "=========================================================================================================\n";
	myFile << "= No  Nama Menu                     Harga     Jumlah        Sub Total                                   =\n";
	myFile << "=========================================================================================================\n";
	for (int a = 0; a < i; a++)
	{
		myFile << a + 1 << "	" << menu[a] << "	" << harga[a] << "		" << porsi[a] << "		" << sub_total[a] << endl;
	}

	myFile << "---------------------------------------------------------------------------------------------------------" << endl << endl;
	myFile << "     Total           " << total_bayar << endl;
	myFile << "     Tunai           " << tunai << endl;
	myFile << "---------------------------------------------------------------------------------------------------------" << endl;
	myFile << "     Kembali         " << kembalian << endl;
	waktu();
	myFile << c << ':' << d << ':' << e << endl;
	myFile << f << ':' << g << ':' << h << endl;
	// menutup program
	myFile.close();
pilih:
	cout << "lagi <y/t> : "; cin >> a;
	if (a == 't' || a == 'T')
	{
		admiin();
		system("cls");
	}
	else if (a == 'y' || a == 'Y')
	{
		goto awal;
		system("cls");
	}
	else
	{
		cout << "pilihan tidak ada!!" << endl << endl;
		goto pilih;
	}
	cin.get();
	return 0;

}

void waktu()
{
	time_t a = time(0);
	tm* b = localtime(&a);

	c = b->tm_hour;
	d = b->tm_min;
	e = b->tm_sec;
	f = b->tm_mday;
	g = 1 + b->tm_mon;
	h = 1900 + b->tm_year;

	cin.get();
	cin.get();

}

