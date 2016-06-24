<properties title="Create tables in markdown" pageTitle="마크다운으로 EMS 문서에 대한 테이블 만들기" description="마크다운으로 테이블을 코딩하는 방법을 설명합니다." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# 마크다운으로 테이블 만들기

방법:
- [ ] #33 사용자 지정 마크다운 참고 구문을 아래 참고에 추가합니다.

문서에서 테이블은 꼭 필요할 때만 사용해야 합니다. 데이터가 정말 테이블 형식인 경우에만 사용합니다.

**참고**
마크다운 테이블의 기능은 텍스트의 긴 문자열 처리를 위해 제한되어 있습니다. 테이블 셀 안에는 단어 잘림 개념이 없습니다. 셀은 단순히 콘텐츠의 전체 너비까지 확장되므로 작은 화면에서 테이블을 보는 것이 어려울 수 있습니다. 적은 규모의 정보에 테이블을 사용하고, 더 긴 콘텐츠의 경우 다른 유용한 방법을 찾아 봅니다.

## 마크다운 테이블 구문
마크다운으로 테이블을 만드는 가장 간단한 방법은 파이프와 하이픈을 사용하는 것입니다. 테이블 머리글을 만들기 위해 각 열의 두 번째 행에는 3개 이상의 하이픈이 필요합니다. 테이블 머리글 텍스트는 자동으로 가운데 정렬되며 굵은 덱트스로 렌더링됩니다.  

 ![1]

마크다운은 대체 테이블 행 음영을 자동으로 렌더링합니다.  
 ![2]

콜론으로 열 맞춤을 적용할 수 있습니다.

  	|:-----|   - this is left aligned (default -- can be omitted)
  	|-----:|   - this is right aligned
  	|:-----:|  - this is centered

바깥쪽 파이프는 선택 사항이며, 테이블의 정확한 렌더링을 위해 텍스트와 파이프를 완벽하게 정렬할 필요는 없습니다. 빠른 서식 지정의 예제는 다음과 같습니다.

 ![3]

마크다운에서 정확하게 읽고 렌더링합니다.  
 ![4]

HTML 테이블을 사용하고 마크다운이 두 테이블 간에 렌더링되지 않는 경우, TABLE 태그를 닫은 후 닫는 BR 태그를 추가해야 합니다.

![5]

마크다운 테이블 생성기( http://www.tablesgenerator.com/markdown_tables)를 사용하면 빠르고 간편하게 마크다운에서 테이블을 만들 수 있습니다.


## 홈으로 돌아가기

- [개요 문서](./../README.md)
- [지침 문서 인덱스](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/table-markdown-1.png
[2]: ./media/table-markdown-2.png
[3]: ./media/table-markdown-3.png
[4]: ./media/table-markdown-4.png
[5]: ./media/break-tables.png


<!--HONumber=Mar16_HO1-->


