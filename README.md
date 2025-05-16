[13:19, 14/05/2025] Matheus Henrique: using System;
using System.Collections.Generic;

public class Estacionamento
{
    private decimal precoInicial;
    private decimal precoPorHora;
    private List<string> veiculos;

    public Estacionamento(decimal precoInicial, decimal precoPorHora)
    {
        this.precoInicial = precoInicial;
        this.precoPorHora = precoPorHora;
        veiculos = new List<string>();
    }

    public void AdicionarVeiculo(string placa)
    {
        veiculos.Add(placa);
        Console.WriteLine($"Veículo {placa} adicionado.");
    }

    public void RemoverVeiculo(string placa, int horas)
    {
        if (veiculos.Contains(placa))
        {
            veiculos.Remove(placa);
            decimal total = precoInicial + precoPorHora * horas;
            Console.WriteLine($"Veículo {placa} removido. Total a pagar: R${total:F2}");
        }
        else
        {
            Console.WriteLine($"Veículo {placa} não encontrado.");
        }
    }

    public void ListarVeiculos()
    {
        if (veiculos.Count > 0)
        {
            Console.WriteLine("Veículos estacionados:");
            foreach (var veiculo in veiculos)
            {
                Console.WriteLine(veiculo);
            }
        }
        else
        {
            Console.WriteLine("Não há veículos estacionados.");
        }
    }

    public void EncontrarVeiculo(string placa)
    {
        if (veiculos.Contains(placa))
        {
            Console.WriteLine($"Veículo {placa} está estacionado.");
        }
        else
        {
            Console.WriteLine($"Veículo {placa} não encontrado.");
        }
    }
}
[13:20, 14/05/2025] Matheus Henrique: class Program
{
    static void Main(string[] args)
    {
        Estacionamento estacionamento = new Estacionamento(5.00m, 2.00m);

        estacionamento.AdicionarVeiculo("ABC1234");
        estacionamento.ListarVeiculos();
        estacionamento.RemoverVeiculo("ABC1234", 3);
        estacionamento.ListarVeiculos();
    }
}# estacionamento-dotnet