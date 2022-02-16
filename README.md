# AngularCalculation

# Web Page for Mathematical Calculations using Angular

## AIM:
To design a dynamic website to perform mathematical calculations using Angular Framwork

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML and CSS in component.html file

### Step 3:

Write typescript to perform the calculations.

### Step 4:

Validate the layout in various browsers.

### Step 5:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## cylindercomponent.html:
```
<style>
    h2{
background-color: rgb(136, 94, 112);
color: rgb(122, 190, 90);
}
.container {
  display: block;
  background-color: #43bdbd;
  min-height: 200px;
  margin-top: 100px;
}
.al{
    text-align: center;
    font-size: 25px;
}

</style>
<div class="container">
<div class="al">
    <h2>VOLUME OF CYLINDER</h2>
    Radius=<input type="text"[(ngModel)]='radius'>Meters<br/>
    Height=<input type="text"[(ngModel)]='height'>Meters<br/>
    <input tAype="button" (click)="onCalculate()" value="CalculateArea"><br/>
    Volume=<input type="text" [value]="volume"> Meters<sup>3</sup><br/>
    volume=π*r^2*h

</div>
</div>
```

## cylindercomponent.ts:
```
import { Component } from "@angular/core";

@Component({
    selector:'Cylinder-Vol',
    templateUrl:'./cylinder.component.html'
})
export class CylinderComponent{
    radius:number;
    height:number;
    volume:number;
    constructor(){
        this.radius=0;
        this.height=0;
        this.volume=0;
    }
    onCalculate(){
        this.volume = 22/7*this.radius**2*this.height
    }
}
```

## rectanglecomponent.html:
```
<style>
    h2{
background-color: rgb(156, 197, 187);
color: rgb(62, 115, 158);
}
.container {
  display: block;
  background-color: #e6bf42;
  min-height: 200px;
  margin-top: 100px;
}
.al{
    text-align: center;
    font-size: 25px;
}

</style>

<div class="container">
    <div class="al">
    <h2>AREA OF RECTANGLE</h2>
    Length=<input type="text"[(ngModel)]='length'>Meters<br/>
    Breadt=<input type="text"[(ngModel)]='breadth'>Meters<br/>
    <input type="button" (click)="onCalculate()" value="CalculateArea"><br/>
    Area=<input type="text" [value]="area"> Meters<sup>2</sup><br/>
</div>

</div>
```
## rectanglecomponent.ts:
```
import { Component } from "@angular/core";

@Component({
    selector:'Rectangle-Area',
    templateUrl:'./rectangle.component.html'
})
export class RectangleComponent{
    length:number;
    breadth:number;
    area:number;
    constructor(){
        this.length=0;
        this.breadth=0;
        this.area=0;


    }
    onCalculate()
    {
            this.area = this.length*this.breadth
    }
}
```
## appcomponent.css:
```
h2{
    text-align: center;
    color: rgb(17, 14, 39);
    margin-top: 10px;


}
.container {
    width: 800px;
    margin-left: auto;
    margin-right: auto;
  }
  .backgd{
    background-color: rgb(234, 247, 162) ;
}
  .footer{
      text-align: center;
      font-size: 30px;
      color: rgb(15, 20, 17);
      background-color: rgb(227, 121, 241);
      margin-top: 10px;
  }
```
## apppcomponent.html:
```
<div class="backgd">
<h2>MATH CALCULATION</h2>
<div class="container">
    
<Rectangle-Area>

</Rectangle-Area>

<Cylinder-Vol>

</Cylinder-Vol>

<div class="footer">DEVELOPED BY: Paarkavy B</div>

</div>

</div>
```
## appcomponent.spec.ts:
```
import { TestBed } from '@angular/core/testing';
import { AppComponent } from './app.component';

describe('AppComponent', () => {
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  });

  it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });

  it(`should have as title 'mathcalculation'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('mathcalculation');
  });

  it('should render title', () => {
    const fixture = TestBed.createComponent(AppComponent);
    fixture.detectChanges();
    const compiled = fixture.nativeElement as HTMLElement;
    expect(compiled.querySelector('.content span')?.textContent).toContain('mathcalculation app is running!');
  });
});
```
## appcompnent.ts:
```
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'mathcalculation';
}
```
## appmodule.ts:
```
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from './app.component';
import { CylinderComponent } from './cylinder/cylinder.component';
import { RectangleComponent } from './rectangle/rectangle.component';

@NgModule({
  declarations: [
    AppComponent,RectangleComponent,CylinderComponent
  ],
  imports: [
    BrowserModule,FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## OUTPUT WITHOUT CALCULATION:
![output](ac.jpeg)

## OUTPUT WITH CALCULATION:
![ac1](https://user-images.githubusercontent.com/93509383/154204368-c15b101d-e2e5-4de9-b1e4-8388ba110ca2.jpeg)



## Result:
Thus we successfully designed the dynamic website to perform mathematical calculations using Angular Framwork.
