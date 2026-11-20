## Question 1

```text
...

./build/TME4 -m resize -i input_images -o output_reference
Image resizer starting with input folder 'input_images', output folder 'output_reference', mode 'resize', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 10
Thread 140608190085760 (main): 8054 ms CPU
Total runtime (wall clock): 8726 ms
Memory usage: Resident: 58.7 MB, Peak: 148 MB
Peak RSS (bytes): 155439104
Total CPU time across all threads: 8054 ms


./build/TME4 -m pipe -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 10
Thread 140034751592128 (treatImage): 7195 ms CPU
Thread 140034805758592 (main): 2 ms CPU
Total runtime (wall clock): 7801 ms
Memory usage: Resident: 52.7 MB, Peak: 142 MB
Peak RSS (bytes): 149291008
Total CPU time across all threads: 7197 ms

OK : 41 fichiers dans chaque dossier.
```

## Question 2

```text
...

timeout 10 ./build/TME4 -m pipe -q 1 -i input_images -o output_images

Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 1
Thread 140592484972224 (treatImage): 7303 ms CPU
Thread 140592539110016 (main): 3 ms CPU
Total runtime (wall clock): 7890 ms
Memory usage: Resident: 52.9 MB, Peak: 143 MB
Peak RSS (bytes): 149483520
Total CPU time across all threads: 7306 ms

Inverser 2 et 3 :
timeout 40 ./build/TME4 -m pipe -q 1 -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 1
-> Erreur aucune image

Inverser 3 et 4:
timeout 40 ./build/TME4 -m pipe -q 1 -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 1
Thread 139930164524736 (treatImage): 0 ms CPU
-> Erreur aucune image

Inverser 4 et 5 :
timeout 40 ./build/TME4 -m pipe -q 1 -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 1
Il y'a 41 images mais erreur
```

## Question 3

```text
...
./build/TME4 -m pipe_mt -n 1 -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe_mt', nthreads 1, nbread 1, nbresize 1, nbwrite 1, queue_size 10
Thread 140401004508864 (treatImage): 8679 ms CPU
Thread 140401050315392 (main): 6 ms CPU
Total runtime (wall clock): 9522 ms
Memory usage: Resident: 51.8 MB, Peak: 141 MB
Peak RSS (bytes): 148029440
Total CPU time across all threads: 8685 ms
OK : 41 fichiers dans chaque dossier.


./build/TME4 -m pipe_mt -n 4 -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'pipe_mt', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 10
Thread 140535645857472 (treatImage): 2695 ms CPU
Thread 140535637464768 (treatImage): 2894 ms CPU
Thread 140535654250176 (treatImage): 3145 ms CPU
Thread 140535629072064 (treatImage): 3182 ms CPU
Thread 140535702620800 (main): 3 ms CPU
Total runtime (wall clock): 3547 ms
Memory usage: Resident: 120 MB, Peak: 325 MB
Peak RSS (bytes): 340877312
Total CPU time across all threads: 11919 ms
OK : 41 fichiers dans chaque dossier.


```

## Question 4

```text
...
```

## Question 5

```text
...
./build/TME4 -m mt_pipeline -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'mt_pipeline', nthreads 4, nbread 1, nbresize 1, nbwrite 1, queue_size 10
Thread 139677896013504 (reader): 6415 ms CPU
Thread 139677887620800 (resizer): 18 ms CPU
Thread 139677879228096 (saver): 880 ms CPU
Thread 139677950085760 (main): 3 ms CPU
Total runtime (wall clock): 6466 ms
Memory usage: Resident: 61.3 MB, Peak: 192 MB
Peak RSS (bytes): 201437184
Total CPU time across all threads: 7316 ms

~/Documents/L3/PSCR/PSCR-TME/TME4 master* 
❯ ./check.sh output_reference output_images
OK : 41 fichiers dans chaque dossier.
```

## Question 6

```text
...
/build/TME4 -m mt_pipeline -r 4 -s 4 -w 4 -i input_images -o output_images
Image resizer starting with input folder 'input_images', output folder 'output_images', mode 'mt_pipeline', nthreads 4, nbread 4, nbresize 4, nbwrite 4, queue_size 10
Thread 140248984045248 (reader): 2835 ms CPU
Thread 140248992437952 (reader): 2937 ms CPU
Thread 140249000830656 (reader): 3232 ms CPU
Thread 140249009223360 (reader): 3289 ms CPU
Thread 140248950474432 (resizer): 11 ms CPU
Thread 140248958867136 (resizer): 5 ms CPU
Thread 140248975652544 (resizer): 11 ms CPU
Thread 140248967259840 (resizer): 12 ms CPU
Thread 140248925296320 (saver): 573 ms CPU
Thread 140248933689024 (saver): 242 ms CPU
Thread 140248916903616 (saver): 495 ms CPU
Thread 140248942081728 (saver): 506 ms CPU
Thread 140249057639040 (main): 3 ms CPU
Total runtime (wall clock): 3514 ms
Memory usage: Resident: 238 MB, Peak: 450 MB
Peak RSS (bytes): 471556096
Total CPU time across all threads: 14151 ms

~/Documents/L3/PSCR/PSCR-TME/TME4 master* 
❯ ./check.sh output_reference output_images

OK : 41 fichiers dans chaque dossier.
```

## Question 7

```text
...
```

## Question 8

```text
...
```

## Question 9

```text
...
```
