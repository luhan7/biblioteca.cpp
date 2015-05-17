

void main() {


	setlocale(LC_ALL, ".ACP");

	int opc, clave[15], ejemplares[15], clavebus, bus, x;
	char titulo[15][50], editorial[15][50];

	do {
		system("cls");
		printf("1) Altas.\n"
			"2) Consultas generales.\n"
			"3) Consulta por clave.\n"
			"4) Modificación.\n"
			"5) Bajas. \n"
			"6) Salir. \n");
		scanf("%d", &opc);

		switch(opc) { 

		case 1: 
				system("cls");
				if(cont<15) {
				printf("\nClave: ");
				scanf("%d", &clave[cont]); 
				repeticion(clave);
				printf("Título: ");
				fflush(stdin);
				gets(titulo[cont]);
				printf("Editorial: ");
				fflush(stdin);
				gets(editorial[cont]);
				printf("Ejemplares disponibles: "); 
				scanf("%d", &ejemplares[cont]);

				cont++; }

				else
					printf("\nYa ha alcanzado el número máximo de registros.\n");

				break;

		case 2:
				system("cls");
				ordenar(clave, titulo, editorial, ejemplares);
				consultagen(clave, titulo, editorial, ejemplares);
				system("pause");
				break;

		case 3: 
				system("cls");
				printf("\nIngrese la clave a buscar: ");
				scanf("%d", &clavebus);
				bus= buscar(clave, clavebus);
				consultaesp(clave, titulo, editorial, ejemplares, bus);
				printf("\n");
				system("pause");
				break;

		case 4:
				system("cls");
				printf("Clave a modificar: ");
				scanf("%d", &clavebus);
				//Puede incluír búsqueda por nombre.
				bus=buscar(clave, clavebus);
				if (bus!=-1) {
					modificar(clave, titulo, editorial, ejemplares, bus);
						}
				else
					printf("\nNo sé encontró.\n");
					system("pause>null");
				break;

		case 5: 
				system("cls");
				printf("Ingrese clave de libro a eliminar: ");
				scanf("%d", &clavebus);
				bus= buscar(clave, clavebus);
				eliminar(clave, titulo, editorial, ejemplares, bus);
				printf("Registro eliminado.\n\n");
				system("pause");
				break;

		default: printf("\n\n      ¡Gracias!\n\n");
				break;

		}
	}
	while(opc!=6);
	system("pause");
}




