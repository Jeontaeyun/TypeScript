---
description: '"완벽이란 없다. 하지만, 그렇다고 완벽해지려고 노력하는 것이 의미 없는 일은 아니다."'
---

# Intro

## 개요

 이 문서는 자바스크립트와 타입스크립트 언어와 실제 프로그램에서의 활용에 초점을 맞추어 언어에 대한 개념과 활용법을 반복 학습하기 위해서 작성되었습니다. 이 문서를 작성하는 가이드라인은 크게 다음과 같습니다.

1. 자바스크립트와 타입스크립트 언어 자체에 초점을 맞추어 작성할 것입니다.
2. 최신 ECMAScript의 문법에 대한 설명을 추가할 것 입니다.
3. 해당 언어를 사용하여 어떤 동작을 구현할 수 있는지에 대해 설명할 것 입니다.

### 01. 자바스크립트와 타입스크립트 언어

 자바스크립트와 타입스크립트를 배우면서, 자주 반복하는 문법과 표현식에 대해서 깊은 고민이 없이 자연스럽게 반복 사용한다는 것을 알게되었습니다. 하지만, 어떤 언어든 한 언어에 대해서 심층적인 이해를 하는 것이 나의 개발 실력을 향상하는데 조금 더 좋은 영향을 줄 것이라는 생각이 문득 들었습니다.

 프로그래밍 언어 뿐만 아니라 외국어를 공부할 때에도 우리는 보통 이론에만 치우치거나 아니면 실제 사용\(실전\)에만 치우쳐서 공부를 경향이 있습니다. 

 가령 외국에서 오래 산 사람들은 영어를 자연스럽게 잘 말하지만 문법적 지식이 부족해서 조금 더 높은 수준의 창의활동에 문제를 겪을 수 있습니다. 가령 글쓰기, 카피라이팅, 발표 등이 그렇습니다. 저자는 한국어를 유창하게 하는 한국인이지만, 발표를 할 때 발표를 위한 말하기 방법을 다시 배워야 한다는 것이 문득 생각났습니다.

 반면 이론적인 외국어 공부만 열심히 하는 학습법에도 큰 문제가 있습니다. 이론적인 원리는 알지만 막상 실질적인 문제가 생겼을 때 지식을 활용하는 방법을 모른다면, 그 지식은 쓸모가 없는 지식입니다.

 이 문서는 이러한 생각을 바탕으로 시작합니다. 언어에 대한 깊은 이해를 하기 위해 하루에 작은 개념을 하나 씩 정리하고 이를 반복학습하며 문서를 만들어 갈 것입니다. 또한 해당 개념을 실제 구현에 적용해 나가는 예시를 정리하여 해당 개념을 통해 문제를 해결하는 활용법을 익힐 것 입니다.

### 02. ECMAScript 문법

 몇 몇 자바스크립트 입문서를 보면 자바스크립트의 최신 문법\(ES+\)에 대한 설명이 없는 것이 많았습니다. 처음 자바스크립트를 접하는 초심자를 대상으로 작성했기 때문이지만 자바스크립트를 배우고 난 후 실제 개발에서 느끼는 괴리감과 허들이 높았습니다. 따라서 이 문서에서는 최신 자바 스크립트 문법을 바로 소개하며, ES+ 이전과 비교하여 왜 이러한 문법이 생겼는지에 대한 배경을 소개할 것입니다.

### 03. 실제 프로그램 구현에 대한 활용 

 웹 프로그래밍을 위해서 자바스크립트를 배우게 된 후 우리는 리액트, 앵귤러, 뷰와 같은 프레임 워크를 만나게 될 것 입니다. 혹은 Node.js를 배워 웹 프로그래밍 언어로 사용하는 자바스크립트가 아닌 시스템 설계를 위한 혹은 서버 구현을 위한 자바스크립트를 마주할 수 있습니다. 이 때, 해당 기능을 통해서 주로 어떤 구현을 할 수 있는지와 어떤 문제를 해결할 수 있는지에 대한 것을 소개할 것입니다.

