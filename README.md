# Tutorial 11 - kubernetes
AdvPro B - Marvel Martin Everthard - 2206081345

## Reflection on Hello Minikube
1. _**Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?**_

- _**Before exposed:**_
![Before](assets/images/Before.png)


- _**After exposed:**_
![After](assets/images/After.png)

- _**After opening several times:**_
![AfterSeveral](assets/images/AfterSeveral.png)

Sebelum aplikasi diakses melalui _service_, log hanya menunjukkan pesan awal bahwa server HTTP dan UDP telah start pada port 8080 dan 8081. Setelah aplikasi diakses melalui layanan dan permintaan HTTP dilakukan, log menunjukkan pesan tambahan yang menunjukkan permintaan GET HTTP yang dibuat ke aplikasi pada waktu yang berbeda. Jumlah log bertambah setiap kali aplikasi dibuka, seperti yang ditunjukkan oleh pesan log tambahan untuk setiap permintaan GET HTTP yang dilakukan ke aplikasi.


2. _**Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to `kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?**_

Opsi `-n` dalam `kubectl get` digunakan untuk menentukan namespace di mana resource akan ditampilkan. Ketika dijalankan tanpa menyertakan opsi -n, maka kubectl get akan menampilkan resource dari namespace default. Membuat sumber daya di namespace dengan value kube-system menggunakan opsi `-n kube-system` untuk melihatnya akan menampilkan daftar pod dan layanan yang dibuat di namespace kube-system. 