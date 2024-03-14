# MetodosNumericosT3

Eliminación Gaussiana
  El método de eliminación de Gauss-Jordan se refiere a una estrategia utilizada para obtener la forma escalonada por filas de una matriz. 
  El objetivo es escribir la matriz A A con el número 1 como entrada en la diagonal principal y con todos los ceros debajo.
Algoritmo:
  Paso de Eliminación hacia adelante:
    Para cada fila i desde 1 hasta n:
      Encuentra el máximo elemento en la columna i (incluida la fila actual) y llámalo pivote.
      Si el pivote es cero, no se puede continuar, ya que implica una división por cero.
      Intercambia la fila actual con la fila que contiene el pivote máximo, si es necesario.
      Para cada fila j desde i + 1 hasta n:
        Calcula el factor de eliminación como el elemento en la fila j, columna i dividido por el pivote.
        Resta factor * fila_i de la fila j, para hacer cero el elemento debajo del pivote.
  Paso de Sustitución hacia atrás:
    Para cada fila i desde n hasta 1:
      Encuentra la solución de la ecuación correspondiente al término independiente.
      Resta los términos ya resueltos multiplicados por sus coeficientes correspondientes de la ecuación actual.
      Divide el término independiente por el coeficiente del término de la incógnita actual, para encontrar su solución.
  Las soluciones encontradas representan las incógnitas del sistema de ecuaciones lineales original.
Implementación:
public class EliminacionGaussiana {

    public static void main(String[] args) {
        double[][] matriz = {{2, 1, -1, 8},
                              {-3, -1, 2, -11},
                              {-2, 1, 2, -3}};
        
        double[] soluciones = resolverSistema(matriz);
        
        System.out.println("Soluciones:");
        for (int i = 0; i < soluciones.length; i++) {
            System.out.println("x" + (i+1) + " = " + soluciones[i]);
        }
    }
    
    public static double[] resolverSistema(double[][] matriz) {
        int n = matriz.length;
        double[] soluciones = new double[n];
        
        // Paso de eliminación hacia adelante
        for (int i = 0; i < n; i++) {
            // Encuentra el máximo pivote en la columna actual
            int maxIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (Math.abs(matriz[j][i]) > Math.abs(matriz[maxIndex][i])) {
                    maxIndex = j;
                }
            }
            
            // Intercambia filas si es necesario
            double[] temp = matriz[i];
            matriz[i] = matriz[maxIndex];
            matriz[maxIndex] = temp;
            
            // Hacer ceros por debajo del pivote
            for (int j = i + 1; j < n; j++) {
                double factor = matriz[j][i] / matriz[i][i];
                for (int k = i; k < n + 1; k++) {
                    matriz[j][k] -= factor * matriz[i][k];
                }
            }
        }
        
        // Paso de sustitución hacia atrás
        for (int i = n - 1; i >= 0; i--) {
            soluciones[i] = matriz[i][n] / matriz[i][i];
            for (int j = i - 1; j >= 0; j--) {
                matriz[j][n] -= matriz[j][i] * soluciones[i];
            }
        }
        
        return soluciones;
    }
}
