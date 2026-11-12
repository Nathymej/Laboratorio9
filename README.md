# Laboratorio9

#include <fstream>
#include <iostream>
#include <string>
using namespace std;


int main () {
    string frase;
    cout << "Ingrese una frase: ";
    getline(cin, frase);
    
    ofstream salida("diario.txt", ios::app);
    if (!salida) {
        cerr << "Error al abrir el archivo." << endl;
        return 1;
    }
    salida << frase << endl;
    salida.close();

    ifstream entrada("diario.txt");
    string linea;
    cout << "Contenido del archivo diario.txt:" << endl;
    while (getline(entrada, linea)) {
        cout << linea << endl;
    }
    entrada.close();
    return 0;
}
