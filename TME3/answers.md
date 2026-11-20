## Machine de mesure

Collez ici le bloc produit par `./machine-info.sh`, puis complétez le contexte de mesure.

## Machine de mesure

```text
Date : 2026-11-18 08:15 UTC
Système : Linux 7.2.14-zen1-1-zen x86_64
Distribution : Arch Linux
CPU logiques (système) : 8
CPU : Intel(R) Core(TM) i5-8265U CPU @ 1.60GHz
Threads par cœur : 2
Cœurs par socket : 4
Sockets : 1
Fréquence maximale annoncée (MHz) : 3900.0000
CPU logiques disponibles pour ce processus : 8
RAM visible : 7.6 GiB
Compilateur par défaut : c++ (GCC) 16.2.1 20260810
```

À compléter : Debug/Release, machine native/VM/WSL/conteneur, charge concurrente.
La fréquence réelle varie avec la charge, le turbo et la température.

## Question 1

```text
Trace à compléter.

Preparing to parse ../WarAndPeace.txt (mode=freqstd N=4), containing 3235342 bytes
Total runtime (wall clock) : 2975 ms

Preparing to parse ../WarAndPeace.txt (mode=partition N=4), containing 3235342 bytes
Total runtime (wall clock) : 3293 ms

../check.sh freqstd.freq partition.freq
All files are identical
```

## Question 2

```text
~/Documents/L3/PSCR/PSCR-TME/TME3 master* 
❯ ./build-debug/countword ./WarAndPeace.txt mt_naive
Preparing to parse ./WarAndPeace.txt (mode=mt_naive N=4), containing 3235342 bytes
Segmentation fault         (core dumped) ./build-debug/countword ./WarAndPeace.txt mt_naive

~/Documents/L3/PSCR/PSCR-TME/TME3 master* 
❯ ./build-debug/countword ./WarAndPeace.txt mt_naive
Preparing to parse ./WarAndPeace.txt (mode=mt_naive N=4), containing 3235342 bytes
Total runtime (wall clock) : 1392 ms
```

## Question 3

```text
~/Documents/L3/PSCR/PSCR-TME/TME3 master* 
❯ ./build-debug/countword ./WarAndPeace.txt mt_atomic
Preparing to parse ./WarAndPeace.txt (mode=mt_atomic N=4), containing 3235342 bytes
Segmentation fault         (core dumped) ./build-debug/countword ./WarAndPeace.txt mt_atomic

~/Documents/L3/PSCR/PSCR-TME/TME3 master* 
❯ ./build-debug/countword ./WarAndPeace.txt mt_atomic
Preparing to parse ./WarAndPeace.txt (mode=mt_atomic N=4), containing 3235342 bytes
Total runtime (wall clock) : 1834 ms
```

## Question 4

```text
./build-debug/countword ./WarAndPeace.txt mt_mutex
Preparing to parse ./WarAndPeace.txt (mode=mt_mutex N=4), containing 3235342 bytes
Total runtime (wall clock) : 1327 ms
```

## Question 5

```text
Trace à compléter.
```

## Question 6

```text
Trace à compléter.
```

## Question 7

```text
Trace à compléter.
```

## Question 8

```text
Trace à compléter.
```

## Question 9

```text
Trace à compléter.
```

## Question 10

```text
Trace à compléter.
```

## Question 11

```text
Trace à compléter.
```
