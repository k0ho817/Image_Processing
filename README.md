# OpenCV-Python으로 배우는 영상 처리 및 응용
<hr/>

## 목차
### 01. [영상처리 개요](#01-영상처리-개요)
- #### 1.1 [영상처리란 무엇인가?](#11-영상처리란-무엇인가-1)
- #### 1.2 [영상처리의 수준](#12-영상처리의-수준-1)
- #### 1.3 [영상처리의 역사](#13-영상처리의-역사-1)
- #### 1.4 [영상처리 관련 분야](#14-영상처리-관련-분야-1)
- #### 1.5 [영상의 형성 과정](#15-영상의-형성-과정-1)
- #### 1.6 디지털 영상의 표현과 영상처리
- #### 1.7 영상처리 응용 분야
### 02. OpenCV 인터페이스

<hr/>

## 01. 영상처리 개요
### 1.1 영상처리란 무엇인가?

이미지는 작은 컬러의 점들의 집합이다.   
작은 컬러의 점들 = 화소

> 디지털영상처리는 입력된 디지털영상을 어떤 목적을 위해   
수학적 연산을 이용해 화소들에 대해 변화를 주어 처리하는 기술이다.

디지털 영상은 밝기값과 위치값을 가진 이정 수의 화소(pixel)들로 구성되어 있다.   

### 1.2 영상처리의 수준
   
처리 결과가 영상의 특성들이면  이다.

***저 수준의 영상처리(low-level image processing)***
* 처리 결과가 영상 자체
* ex)
    * 영상 향상(image enhancement) : 잡음을 제거하거나 영상을 사람드르이 눈에 보기 좋게 향상 시키는 영상처리

***고 수준의 영상처리(high-level image processing)***
* 처리 결과가 영상의 특성들
* ex)
    * 영상분할, 특징추출, 영상표현, 물체인식
* 컴퓨터 비전(Computer Vision) 분야와 겹치게 됨

<table>
    <tr>
        <td>영상획득</td>
        <td rowspan="5">저 수준의 영상처리<br>(좁은 의미의 영상처리)</td>
    </tr>
    <tr>
        <td>영상향상</td>    
    </tr>
    <tr>
        <td>영상복원</td>
    </tr>
    <tr>
        <td>변환처리</td>
    </tr>
    <tr>
        <td>영상압축</td>
    </tr>
        <tr>
        <td>영상분할</td>
        <td rowspan="3">고 수준의 영상처리<br>(컴퓨터 비전)</td>
    </tr>
        <tr>
        <td>영상표현</td>
    </tr>
        <tr>
        <td>영상인식</td>
    </tr>
</table>

### 1.3 영상처리의 역사
* 1920년대 초
    * 런던-뉴욕간 해저 케이블을 통한 신문사들의 사진정송 사례
    * 영상처리의 시작
* 1940~1950년대
    * 폰 노이만 디지털 컴퓨터 개념의 시작
    * 1948년 트렌지스터의 개발
    * 1958년  마이크로프로세서의 발명
    * 프로그램의 언어의 발달과 운영체제 등의 소프트웨어 기술에 힘입어 오늘날의 디지털 영상처리가 실제로 가능하게 됨
* 1960~1970년대
    * 1964년 아폴로 계획당시 JPL연구소에서 훼손된 영상의 복원 연구 과정에서 본격적인 디지털 영상 처리가 시작됨
    * CT, MRI 등의 의료 분야와 원격 자원탐사, 우주 항공과 관련하여 영상처리 분야가 더욱 발전
* 1980~1990년대
    * 브라우저의 출시로부터 시작된 본격적인 인터넷 시대
    * 영상검색, 영상전송, 영상광고, 컴퓨터 그래픽스, 디지털 카메라의 보급과 연관하여 컴퓨터 비전 등, 영상처리의 응용분야 확장
    * VSLI과 같은 하드웨어 발달
* 2000년대 이후
    * 오늘날 산업 전 분야에서 사용되지 않는 분야가 거의 없을 정도로 발전
    * 스마트폰의 보급으로 스마트폰에 내장된 카메라로 누구나 영상을 쉽게 얻을 수 있는 환경
    * 영상처리 기술은 모든 곳에서 쉽게 만날 수 있게 됨

### 1.4 영상처리 관련 분야
영상처리는 컴퓨터 비전, 컴퓨터 그래픽스 분야와 서로 관련이 있다.

* 영상 - 영상 : 영상처리
* 영상 - 서술 : 컴퓨터 비전
* 서술 - 영상 : 컴퓨터 그래픽스

### 1.5 영상의 형성 과정
> 영상은 위치값과 밝기값을 가진 일정한 수의 화소들의 모임으로 정의한다.

영상을 $f(x,y)$로 표시할때 $(x,y)$는 위치를 가리키는 좌표값이다. $f(\;)$는 해당 위치의 밝기 값이다.<br>   
![디지털 영상 형성 과정](https://private-user-images.githubusercontent.com/53679360/332992421-3a5a3e77-6a27-40b7-a4a1-62f57667200a.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTY3NjA2MTQsIm5iZiI6MTcxNjc2MDMxNCwicGF0aCI6Ii81MzY3OTM2MC8zMzI5OTI0MjEtM2E1YTNlNzctNmEyNy00MGI3LWE0YTEtNjJmNTc2NjcyMDBhLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA1MjYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNTI2VDIxNTE1NFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQ5NTBjZGVhM2ViMDQwMWMxNjRiOTZlMTA5MGNhZjUzYmMxNDM5ZWUwNWE3NjY3Y2I5OGI3MjBhMzliYjc1OTEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.Wi-A6sk4pHmTBc-s-y-XwnAdsHiIiQF7DEKPf2K4K_k)<br>   
영상이 형성되기 위해서는 빛이 물체에 비치고, 물체는 빛을 받는다.  
그 물체에 비친 빛의 일부가 반사되어 카메라 센서에 들아가 영상을 형성한다.  
물체의 표면의 반사량에 따라 카메라에 들어가는 빛의 양이 다르기 때문에 영상 $f(x,y)$는 다음과 같은 식으로 형성된다.
$$f(x,y)=i(x,y)*r(x,y)$$   
* $i(x,y)$ : 물체에 비친 조명의 세기
* $r(x,y)$ : 반사 계수 (0~1)   

디지털 영상을형성하기 위해서 ***표본화sampling***와 ***양자화quantization***란 두 단계가 필요하다.

* 표본화 (sampling) : 카메라 해상도에 해당되는 유한개의 화소의 수만큼 입력 값을 취하는 것
* 양자화 (quantization) : 표본화된 화소의 값을 디지털 화소로 표현하는 단계

![영상 형성을 위한 표본화와 양자화 단계](https://private-user-images.githubusercontent.com/53679360/333911777-501330dd-2ddf-4394-b7eb-168a3d83f011.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTY3NjA2NjUsIm5iZiI6MTcxNjc2MDM2NSwicGF0aCI6Ii81MzY3OTM2MC8zMzM5MTE3NzctNTAxMzMwZGQtMmRkZi00Mzk0LWI3ZWItMTY4YTNkODNmMDExLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA1MjYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNTI2VDIxNTI0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWZjYTk5N2E5MjgxMzA2NjQ2Y2ZmZGFjNDZjMDZhMDg3MDVjYmIyNjA0YWZlN2U0MTIxZDE3OWFkNzA3YmZkM2UmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.eyqasUYes-Kd3l6dWhsSJA4mX_uyoSYFWCPxXTbfYO4)

표본화와 양자화를 거친 영상은 일정수의 화소(pixel)들의 집합인 $M*N$ 크기의 영상으로 표현된다. 그리고 원점의 위치는 $(x,y) = (0,0)$인 왼쪽 위 코너에 있다.

표본화 수에 따라 세로, 가로의 크기인 M과 N이 결정된다. 그리고 각 화소의 양자화 수준에 따라 밝기값의 수준(gray-level)이 정해진다. $k$ 비트로 양자화 되었다면, 밝기값의 수준 $L=2^k$을 가진다.

화소수가 $M*N$개 이고, 한 개의 화소가 $k$비트로 표현되는 영상이 필요로 하는 저장공간 S는 $S=M*N*k$ 비트이다.

입력 영상 $f(x,y)$에 대하여 각종 영상 처리를 $T[\;\;]$로 표현할때, 일반적인 영상 처리($g(x,y)$)는 다음과 같이 표현할 수 있다.   
$$g(x,y) = T[f(x,y)]$$

* $g(x,y)$ : 처리된 출력 영상
* $f(x,y)$ : 입력 영상
* $T[\;\;]$ : 화소처리, 영역처리, 기하학 처리 등