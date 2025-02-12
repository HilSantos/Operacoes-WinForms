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
    }
}
