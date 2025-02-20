# Operacoes-WinForms
Atividades usando o metodo "Operações" do Windows Forms

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;



namespace CalculoNetflix
{
    public static class Operacoes
    {
        // Método para calcular o valor anual
        public static decimal CalcularValorAnual(decimal valorMensal)
        {
            return valorMensal * 12;
        }
    }
}
        // Metodo para calcular o tempo de viagem
namespace CalculoViagem
{
    public static class Operacoes
    {
        // Método para calcular o tempo de viagem
        public static double CalcularTempoViagem(double distancia, double velocidadeMedia)
        {
            if (velocidadeMedia <= 0)
                throw new ArgumentException("A velocidade média deve ser maior que zero.");

  return distancia / velocidadeMedia;
        }

  // Método para calcular o combustível necessário
        public static double CalcularCombustivelNecessario(double distancia, double consumoMedio)
        {
            if (consumoMedio <= 0)
                throw new ArgumentException("O consumo médio deve ser maior que zero.");

  return distancia / consumoMedio;
        }

  // Método para calcular a diferença entre dois horarios
        public static TimeSpan CalcularDiferencaHorarios(DateTime horarioInicial, DateTime horarioFinal)
        {
            if (horarioFinal < horarioInicial)
            {
                throw new ArgumentException("O horário final deve ser maior que o horário inicial.");
            }

  return horarioFinal - horarioInicial;
        }

  // Método para calcular o consumo médio
        public static double CalcularConsumoMedio(double distancia, double combustivelGasto)
        {
            if (combustivelGasto <= 0)
            {
                throw new ArgumentException("A quantidade de combustível gasto deve ser maior que zero.");
            }

  return distancia / combustivelGasto;
        }

  // Cotação fixa (exemplo)
        private const double CotacaoDolar = 5.0; // 1 USD = 5 BRL
        private const double CotacaoEuro = 6.0;  // 1 EUR = 6 BRL

  // Método para converter reais para dólar
        public static double ConverterParaDolar(double valorReais)
        {
            if (valorReais < 0)
            {
                throw new ArgumentException("O valor em reais deve ser maior ou igual a zero.");
            }

  double valorDolar = valorReais / CotacaoDolar;
            return Math.Round(valorDolar, 2); // Arredonda para 2 casas decimais
        }

  // Método para converter reais para euro
        public static double ConverterParaEuro(double valorReais)
        {
            if (valorReais < 0)
            {
                throw new ArgumentException("O valor em reais deve ser maior ou igual a zero.");
            }

  double valorEuro = valorReais / CotacaoEuro;
            return Math.Round(valorEuro, 2); // Arredonda para 2 casas decimais
        }
            // Método para calcular o IMC
        public static double CalcularIMC(double peso, double altura)
        {
            if (peso <= 0 || altura <= 0)
            {
                throw new ArgumentException("O peso e a altura devem ser maiores que zero.");
            }

// Calcula o IMC usando a fórmula: IMC = peso / (altura * altura)
            double imc = peso / Math.Pow(altura, 2);
            return Math.Round(imc, 2); // Arredonda para 2 casas decimais
        }

// Método para converter Celsius para Fahrenheit
        public static double CelsiusParaFahrenheit(double celsius)
        {
            double fahrenheit = celsius * 1.8 + 32;
            return Math.Round(fahrenheit, 2); // Arredonda para 2 casas decimais
        }

// Método para converter Fahrenheit para Celsius
        public static double FahrenheitParaCelsius(double fahrenheit)
        {
            double celsius = (fahrenheit - 32) / 1.8;
            return Math.Round(celsius, 2); // Arredonda para 2 casas decimais
        }
    }

namespace CalculadoraBTU
{
    public static class Operacoes
    {
        // Método para calcular a quantidade ideal de BTUs
        public static int CalcularBTUs(double metragem, int pessoas, int eletronicos, bool solDireto)
        {
            if (metragem <= 0 || pessoas < 0 || eletronicos < 0)
            {
                throw new ArgumentException("Os valores de metragem, pessoas e eletrônicos devem ser maiores ou iguais a zero.");
            }

// Cálculo básico de BTUs
            int btus = (int)(metragem * 600); // 600 BTUs por m²

// Adiciona 600 BTUs por pessoa extra (considerando a primeira pessoa já incluída no cálculo básico)
            if (pessoas > 1)
            {
                btus += (pessoas - 1) * 600;
            }

// Adiciona 600 BTUs por eletrônico ligado
            btus += eletronicos * 600;

// Adiciona 20% se houver incidência de sol direta
            if (solDireto)
            {
                btus = (int)(btus * 1.2);
            }

return btus;
        }

// Método para sugerir o ar-condicionado ideal com base nos BTUs calculados
        public static string SugerirArCondicionado(int btus)
        {
            if (btus < 7000)
                return "Ar-condicionado de 7.000 BTUs";
            else if (btus < 9000)
                return "Ar-condicionado de 9.000 BTUs";
            else if (btus < 12000)
                return "Ar-condicionado de 12.000 BTUs";
            else if (btus < 18000)
                return "Ar-condicionado de 18.000 BTUs";
            else
                return "Ar-condicionado de 24.000 BTUs ou mais";
        }
    }
}
}
}
