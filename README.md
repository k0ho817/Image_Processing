# OpenCV-Python으로 배우는 영상 처리 및 응용
<hr/>

## 목차
### 01. [영상처리 개요](#01-영상처리-개요)
- #### 1.1 [영상처리란 무엇인가?](#11-영상처리란-무엇인가)
- #### 1.2 [영상처리의 수준](#12-영상처리의-수준)
- #### 1.3 영상처리의 역사
- #### 1.4 영상처리 관련 분야
- #### 1.5 영상의 형성 과정
- #### 1.6 디지털 영상의 표현과 영상처리
- #### 1/7 영상처리 응용 분야
### 2. OpenCV 인터페이스

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