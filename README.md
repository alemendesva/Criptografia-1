# Criptografia-1
Criptografia Rot13

public class Criptografia {
    // Função que le um texto do teclado
    static String lerTextoDoTeclado() {
        BufferedReader leitor = new BufferedReader(
                new InputStreamReader (System.in));
        String texto = "";
        try {
            System.out.print("Digte um texto: ");
            texto = leitor.readLine();
        } catch (Exception erro) {
            System.out.println(erro);
        }
        return texto;
    
    }

        // Funcao que encripta um texto com o algoritmo ROT13
        static String encriptar(String texto) {
            String criptograma = "";
            
            for (int i = 0 ; i < texto.length(); i++) {
                char letra = texto.charAt(i);
                int codigoASCII = (int) letra;
                
                if ((codigoASCII < 97 || (codigoASCII > 122))) {
                    criptograma += letra;
                    
                } else {
                    codigoASCII += 13;
                    if (codigoASCII > 122) {
                        codigoASCII -= 26;
                    }
                    criptograma += ((char) codigoASCII);
                }
            }
            
            return criptograma;
        }
            
            // Funcao principal de execucao do programa
            
            public static void main (String[] args) {
                String texto = lerTextoDoTeclado();
                String criptograma = encriptar (texto);
                System.out.println (criptograma);
            }
        
                    
                
            }
