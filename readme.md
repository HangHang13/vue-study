[toc]



# 0713

## vue 설치

```bash
npm install -g vue
```

## vue3 project 시작하기

```bash
vue create project1
```

1. Manually select features 선택하기
2. 라우터
3. 뷰엑스 설정하기
4. 3.x 설정
5. 유저 히스토리 router 히스토리 모드설정
6. Pick linter / formattter config 
   - 코딩 컨벤션 어떤 포멧 가져갈건지
   - **standard**
7. 어떤 시점에 포맷 체크해줄껀지
   1. Lint on save
      - **세이브할떄**
   2. Lint and fix on commit
      - 커밋할때
8. placing config or babel, ESLint etc?
   1. 따로 파일로 관리할지
   2. **패키지.json으로 관리할지**
9. 했던거 저장할지
   1. vue-project로 저장





- 모든 파일들은 app.js에 들어간다.



## eslint 설정 .prettierrc 파일 만들어주기 

1. 패키지 제이슨과 동일한 위치에 prettierrc 파일 만들기

```
{
    "semi": false,
    "bracketSpacing": true,
    "singleQuote": true,
    "useTabs": false,
    "trailingComma": "none",
    "printWidth": 80
}
```



2. 패키지.json에 rules에 "space-before-function-paren" : "off" 입력하기

```json
  "eslintConfig": {
    "root": true,
    "env": {
      "node": true
    },
    "extends": [
      "plugin:vue/vue3-essential",
      "@vue/standard"
    ],
    "parserOptions": {
      "parser": "@babel/eslint-parser"
    },
    "rules": { "space-before-function-paren" : "off"} ////////////////////
  },
```

"space-before-function-paren" : "off" 의미

- 함수 만들때 띄어쓰는 기능 off



## webpackPrefetch:true

- 캐시에 저장해서 빠르게 페이지를 가져올 수 있음

```vue
//index.js

  {
    path: '/about',
    name: 'about',
    // route level code-splitting
    // this generates a separate chunk (about.[hash].js) for this route
    // which is lazy-loaded when the route is visited.
    component: () => import(/* webpackChunkName: "about", webpackPrefetch:true */ '../views/AboutView.vue')
  }
```

![image-20220713205045248](C:\Users\multicampus\AppData\Roaming\Typora\typora-user-images\image-20220713205045248.png)



- 무조건 들어가는 페이지, 거의 무조건 들어갈페이지, 용량이 큰 페이지는 webpackPrefetch 해주기
- 라우터 설계시 중요하다.



## 데이터 바인딩 실습

### Style scoped는 해당 페이지에서만 스타일 적용 가능

- 대기업은 vue 서비스가 어울린다
  - 보수유지 쉬움

### template에서 vue2 vue3차이

```vue
<template>
<div>
    <h1>

    </h1>
    <p></p>
</div>
</template>

```

- vue2의 경우 div 로 안묶어주면 에러난다.
- vue3는 div로 안묶어줘도 에러 안난다.

### vue는 양방향 데이터 바인딩이 가능함



## Vue User Snippets 등록

1. File > Preference > User Snippets 메뉴 이동
2. 검색창에 vue 입력 > vue 선택
3. 아래 코드 입력
