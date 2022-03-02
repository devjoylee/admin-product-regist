<!-- PROJECT LOGO -->
<div align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/3094/3094371.png" alt="Logo" width="80" height="80">
  <h1>어드민 상품등록 페이지</h1>
  <p>
    <a href="wanted-admin-product.netlify.app/">배포 주소 바로가기</a>
    ·
    <a href="https://devjoylee.github.io/admin-registry/">프로젝트 회고 바로가기</a>
  </p>

[![Contributors][contributors-shield]][contributors-url]

[contributors-shield]: https://img.shields.io/github/contributors/devjoylee/admin-product-registry.svg?style=for-the-badge
[contributors-url]: https://github.com/devjoylee/admin-product-registry/graphs/contributors

</div>

<!-- TABLE OF CONTENTS -->
<details align="right">
  <summary>Table of Contents</summary>
    <div><a href="#프로젝트-소개">프로젝트 소개</a></div>
    <div><a href="#기술-스택">기술 스택</a></div>
    <div><a href="#과제-구현-목록">과제 구현 목록</a></div>
    <div><a href="#CRA-구조">CRA 구조</a></div>
    <div><a href="#커밋-컨벤션">커밋 컨벤션</a></div>
    <div><a href="#과제-후기">과제 후기</a></div>
</details>

## 프로젝트 소개

> 소고기 판매 플랫폼의 관리자 페이지를 가정하여 상품 등록 페이지를 구현했습니다.

### member

<table>
  <tr>
        </td>
      <td align="center">
      <a href="https://github.com/LEEHYUNHO2001"
        ><img
          src="https://avatars.githubusercontent.com/LEEHYUNHO2001"
          width="100px;"
          alt=""
        /><br /><sub><b>이현호</b></sub></a>
    <br />
    </td>
    <td align="center">
      <a href="https://github.com/hoonjoo-park"
        ><img
          src="https://avatars.githubusercontent.com/hoonjoo-park"
          width="100px;"
          alt=""
        /><br /><sub><b>박훈주</b></sub></a
      ><br />
    </td>
    <td align="center">
      <a href="https://github.com/Yoon-CH"
        ><img
          src="https://avatars.githubusercontent.com/Yoon-CH"
          width="100px;"
          alt=""
        /><br /><sub><b>윤창현</b></sub></a
      ><br />
    </td>
    <td align="center">
      <a href="https://github.com/devjoylee"
        ><img
          src="https://avatars.githubusercontent.com/devjoylee"
          width="100px;"
          alt=""
        /><br /><sub><b>이주영</b></sub></a
      ><br />
  </tr>
</table>

| 이름   | 담당                                        |
| ------ | ------------------------------------------- |
| 이주영 | 공통 UI 제작, 상품 기본 정보, 이미지 업로드 |
| 박훈주 | 상품 옵션 섹션, 사이드 메뉴바               |
| 이현호 | 상품 정보 고시, 필터 태그(자동 완성)        |
| 윤창현 | 상품 기간, 카테고리, 배송 및 기타 설정      |

<br/>

## 기술 스택

<img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white" style="display:">&nbsp;&nbsp;<img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white">&nbsp;&nbsp;<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">&nbsp;&nbsp;<img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black">

<br/>

## 과제 구현 목록

### 이미지 첨부 기능

상품 썸네일은 **최대 1개,** 상품 대표 이미지는 **여러개** 첨부 가능하도록 기능 구현.

- 파일 업로드 버튼 custom 하기 : **input**의 `id`와 **label**의 `htmlFor`에 같은 id를 입력한 후 input은 `display:none` 해주고 `label` 스타일링.

- 이미지 파일만 첨부 가능하게 : `accept="image/*"` 또는 `accept="image/png"`
- 파일 중복 선택 `multiple`

### 업로드한 이미지 정보 가져오기

- 이미지가 1개 인경우 `e.target.files[0]` 으로 첫번째 파일 정보를 바로 가져온다

- 이미지가 여러개인 경우 `Array.from(e.target.files).map()` <br/>
  `e.target.files` 로 불러온 객체 형식의 데이터를 배열로 바꾸어서 관리해준다.

### useForm.js 과 validation.js을 사용한 폼 구현

validation이라는 유틸함수를 만들고 값이 전달되지 않는 필수 옵션명의 이름을 리턴하도록 작성했다. 그리고 코드의 가독성을 위해 useForm이라는 커스텀 hook을 만들었고 validation에서 리턴된 옵션명을 alert에 출력하는 함수를 리턴하도록 구현했다.

![캡처](https://user-images.githubusercontent.com/68415905/154845357-06d08840-fb5d-455f-8aec-fe1331ce6d80.JPG)

<br/>

## CRA 구조

```markdown
├─components
│ ├─BasicInformation
│ │  
│ ├─ImageSection
│ │  
│ ├─Layouts
│ │  
│ ├─Library
│ │  
│ ├─Period
│ │  
│ ├─ProductInformation
│ │  
│ ├─ProductOption
│ │  
│ └─Setting
│  
├─constants
├─data
├─pages
├─styles
└─utils
```

<br/>

## 커밋 컨벤션

commit 메세지에 깃모지를 추가하여 어떤 작업을 수행했는지 한 눈에 확인할 수 있도록 직관성을 높였습니다.

| 깃모지 | 사용 예시               |
| ------ | ----------------------- |
| 🎉     | init                    |
| 🚚     | 디렉토리 또는 파일 이동 |
| ✨     | 기능 구현               |
| 💄     | CSS 스타일링            |
| ♻️     | 리팩토링                |
| 📝     | Readme 수정             |
| ➕     | 모듈 추가               |
| 🐛     | 버그 해결               |
| 🚑️    | 치명적인 오류 해결      |

출처 : 깃모지(http://gitmoji.dev/)

<br/>

## 과제 후기

### 이주영 🎗

이번 프로젝트는 팀원이 함께 의견을 조율하여 작업 분량을 나누고 각자 맡은 과제를 수행하는 방식으로 진행했습니다. 서로 다른 역할을 맡았지만 비슷한 구조나 공통 상수가 생기면 그때그때 팀원들과 공유하며 작업을 함께 했습니다. 내가 작업하는 부분이 다른 팀원들에게 필요하지 않을까 생각하려고 노력하였고 진정한 협업이란 이런거구나 느낄 수 있었습니다.

### 이현호 😎

요구사항을 꼼꼼하게 읽는것이 중요하다는 것을 일깨워준 프로젝트 입니다. 기능을 구현하더라도 요구사항의 의도와 다르다면 처음부터 다시 구현해야 하기 때문입니다. 불가능해 보이던 기능도 끊임없이 도전하여 성공적으로 구현할 수 있었습니다. 그 후 리팩토링을 진행하며 자주 사용하는 기능은 utils 디렉터리에 넣어 팀원과 함께 사용했습니다.

### 윤창현 ✨

팀을 이루어 진행하는 프로젝트 이기에 팀원들과의 충분한 소통을 통해 4명이지만 통일된 코드와 구조를 완성할 수 있었고, 개발자로서 로직을 구현하는 방법에 대한 깊은 생각과 깃헙을 통한 협업의 중요성을 다시 한 번 느낄 수 있었던 좋은 시간 이었습니다.

### 박훈주 🧛‍♂️

이번 프로젝트에서는 여러 컴포넌트들을 분리하여 각자 맡은 섹션을 작업했습니다. 이러한 과정을 통해 협업을 잘하는, 그리고 “같이 일하기 좋은**” 개발자로 성장하는데 발판이 되어준 것 같습니다. **merge conflict 해결**과 **git rebase\*\*에 대한 이해도를 한 층 더 높일 수 있는 기회였다고 생각합니다. 팀원분들 고생 너무 많으셨습니다 🙂

<p align="right">(<a href="#top">back to top</a>)</p>
