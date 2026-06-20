# Trabalho Prático 2 — Gerenciador de Memória Virtual

Simulador de gerência de memória virtual implementado em C, desenvolvido como trabalho prático da disciplina de Sistemas Operacionais — PUC Minas Campus Betim.

## Estrutura

```text
vm_manager/
├── Makefile
├── README.md
├── include/
│   ├── config.h
│   ├── tlb.h
│   ├── page_table.h
│   ├── memory.h
│   └── statistics.h
├── src/
│   ├── main.c
│   ├── tlb.c
│   ├── page_table.c
│   ├── memory.c
│   └── statistics.c
├── data/
│   └── generate_data.py
└── report/
```

## Funcionalidades Implementadas

- Tradução de endereços lógicos para físicos
- Tabela de páginas com 256 entradas
- TLB com 16 entradas e política de substituição FIFO
- Tratamento de page faults com paginação por demanda
- Substituição de páginas com LRU aproximado (algoritmo de Aging)
- Estatísticas de page fault rate e TLB hit rate

## Gerar arquivos de entrada

Entre no diretório `data` e execute:

```bash
python3 generate_data.py
```

Isso criará:

- `BACKING_STORE.bin`
- `addresses_random.txt`
- `addresses_location.txt`

## Compilação

Na raiz do projeto:

```bash
make
```

## Execução

```bash
./vm < data/addresses_random.txt
```

ou

```bash
./vm < data/addresses_location.txt
```