# Easy-Covid-Vaccination
This is the project I submitted for Technothon 1.0

## **Aim of this Project:**

This project will help us to increase the efficiency and speed of the covid vaccination process.

## **Problems Solved**

The major problem with the current vaccination process is that even when the registration is done people still don't get seats for vaccination so with this project my aim is to ease the seat booking process with the help of image processing and machine learning.

1. During the registration process people can click a photo of their face so that when they visit the vaccination center their face will be scanned to make sure its the same person(because of this no cross-checking and form filling is required)
2. Once the registration is done the program will automatically put you in a queue. when the vaccines get supplied to the center it will automatically book your seat(the system will notify you and then you just have to click a confirm button, if not pressed within 24 hours then the system will book the seat for someone else)
3. With the help of various data the system can make predictions of when the vaccine will be available and how long will it take to book your seat.
4. If a center hasn't received any vaccination dose for too long and there are still people left for vaccination then the system will command vaccine-making companies to give priority to these centers.
5. Mobile applications can be linked to the server so that people can easily register and get regular updates regarding the vaccination process and other details regarding covid 19 using NovelCOVID API.


<mat-form-field class="example-chip-list" appearance="outline">
  <mat-label>Other Benchmark/s BBG Code</mat-label>
  <mat-chip-list #chipList aria-label="Other Benchmark selection">
    <mat-chip
      *ngFor="let benchmark of selectedOtherBenchmarks"
      (removed)="removeBenchmark(benchmark)">
      {{benchmark.bbgCode}} 
      <button matChipRemove>
        <mat-icon>cancel</mat-icon>
      </button>
    </mat-chip>
    <input
      placeholder="Other Benchmark BBG Code"
      #otherBenchmarkInput
      [formControl]="otherBenchmarkControl"
      [matAutocomplete]="auto"
      [matChipInputFor]="chipList"
      [matChipInputSeparatorKeyCodes]="separatorKeysCodes"
      (matChipInputTokenEnd)="addBenchmark($event)"
    />
  </mat-chip-list>
  <mat-autocomplete #auto="matAutocomplete" (optionSelected)="selectedBenchmark($event)">
    <mat-option *ngFor="let option of filteredOtherBenchmarkOptions | async" [value]="option">
      {{ option.bbgCode }} | {{ option.mdsCode }} | {{ option.cinergyCode }}
    </mat-option>
  </mat-autocomplete>
</mat-form-field>
