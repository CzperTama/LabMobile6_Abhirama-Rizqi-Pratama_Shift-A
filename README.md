# LabMobile6_Abhirama-Rizqi-Pratama_Shift-A

Nama        : Abhirama Rizqi Pratama  
Nim         : H1D022099  
Shift Lama  : D  
Shift Baru  : A  

1. Buka file folder.page.html.
2. Pada file tersebut, tambahkan kode HTML untuk menampilkan biodata diri:

```html
<ion-list>
  <ion-item>
    <ion-icon name="person-outline" slot="start"></ion-icon>
    <ion-label>
      <h2>Nama Lengkap</h2>
      <p>Abhirama Rizqi Pratama</p>
    </ion-label>
  </ion-item>
  <ion-item>
    <ion-icon name="card-outline" slot="start"></ion-icon>
    <ion-label>
      <h2>NIM</h2>
      <p>H1D022099</p>
    </ion-label>
  </ion-item>
  <ion-item>
    <ion-icon name="book-outline" slot="start"></ion-icon>
    <ion-label>
      <h2>Program Studi</h2>
      <p>Informatika</p>
    </ion-label>
  </ion-item>
</ion-list>
```

3. Tambahkan kode TypeScript untuk menampilkan jadwal hari ini:
```html
<ion-col>
  <ion-button (click)="toggleSchedule()" expand="block" color="primary">
    <ion-icon slot="start" name="calendar-outline"></ion-icon>
    Jadwal
  </ion-button>
  <ion-card *ngIf="showSchedule">
    <ion-card-header>
      <ion-card-title>Jadwal Hari Ini</ion-card-title>
    </ion-card-header>
    <ion-card-content>
      <ion-list>
        <ion-item>
          <ion-label>Praktikum Pemrograman Mobile</ion-label>
        </ion-item>
      </ion-list>
    </ion-card-content>
  </ion-card>
</ion-col>
```

4. Tambahkan kode TypeScript untuk menyembunyikan atau menampilkan jadwal berdasarkan suatu kondisi:
```typescript
import { Component, inject, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-folder',
  templateUrl: './folder.page.html',
  styleUrls: ['./folder.page.scss'],
})
export class FolderPage implements OnInit {
  public folder!: string;
  private activatedRoute = inject(ActivatedRoute);
  showSchedule = false;

  ngOnInit() {
    this.folder = this.activatedRoute.snapshot.paramMap.get('id') as string;
  }

  toggleSchedule() {
    this.showSchedule = !this.showSchedule;
  }
}
```
Pada nomor 4 diimplementasikan pada nomor 3 pada kode HTML dengan menggunakan `*ngIf="showSchedule"`.

5. Jalankan aplikasi dengan perintah `ionic serve` dan periksa hasilnya.


# Screenshot
<div style="display: flex; justify-content: space-between;">
  <img src="assets/images/prtsc_mobile.png" width="19%">
  <img src="assets/images/prtsc_mobileshowSchedule.png" width="19%">
  <img src="assets/images/prtsc_web.png" width="19%">
  <img src="assets/images/prtsc_web_showSchedule.png" width="19%">
</div>
