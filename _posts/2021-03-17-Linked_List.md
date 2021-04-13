---
layout: post
title: "연결리스트(Linked_List) 구조"
date: 2021-03-17
author: "ERC재이수"
categories: Data_Structures
---

# 1. 개요

**List는 중복은 허용되나 순서가 지켜지는**자료구조이다.
2가지로 나뉘는데 우리가 잘 아는 **Arraylist**와 이번에 다룰 **Linked List**가 있다.

C에서 static array들을 써왔다면 몇몇 불편한 점을 겪었을 것이다. 예를 들면 크기가 고정되어서 공간이 남거나 부족한점, 데이터 삽입과 삭제가 불편한점 등등. 동적할당을 한다 해도 사이즈 조정이 필요한 순간이 있었을 것이다.

이에 대한 대책으로 **Linked List**가 만들어졌다.

# 2. 원리

아주 간단하게 말하면, **Node**(데이터와 포인터의 묶음)들을 한 줄로 세운 것이다.

정확히 Node에는 데이터와 그 다음 Node를 가리키는 포인터로 구성되어 있다. 그래서 array처럼 메모리상 실제로 Node 바로 옆에 다른 Node가 없을 수도 있다. 밑의 이미지를 참고하자.

<a href="/assets/Linked_List/1.PNG" data-lightbox="linkedlist1" data-title="출처: 그림">
    <img src="/assets/Linked_List/1.PNG" title="1">
</a>

다양하게 singly linked list, circular, doubly, linked queue and stack 등이 있지만 여기서는 singly linked list만 설명할것이다.

#  3. 기능

C나 C++ 같은 경우 struct로 node를 만들어 main코드에서 사용해주면 되고, 자바는 node class를 하나 만들어 다른 class에서 사용해준다.

## 1) Node class(또는 struct)

### Node(int item)

data에 item을 넣고, 다음 node link는 null로 한다.

## 2) Linked list class

node 타입의 **head** 변수를 하나 만들어준다.

### Linked list() 
맨 처음 Node인 head를 null로 설정한다.

### void Insert(item) 

* list 맨 마지막에 삽입하는 경우

    새로운 node를 할당 받고, head에서 끝까지 이동한 후, 이전 노드의 link에다가 연결 시켜준다.

    list가 비었을 경우 head에 새로운 노드를 넣어주면 된다.

* list 중간에 연결하는 경우

    1. 새로운 노드를 할당받는다.
    2. data 설정하기
    3. 새로운 노드의 link를 이전 노드(이하 P) 의 링크(P가 가리키던 노드) 로  정한다.
    4. P의 링크를 새로운 노드로 한다.

참고할 이미지는 새로운 노드를 기존 노드 후에 삽입한 것이다.

<a href="/assets/Linked_List/2.PNG" data-lightbox="linkedlist1" data-title="출처: 그림">
    <img src="/assets/Linked_List/2.PNG" title="2">
</a>

### void Delete()

* list 마지막을 삭제할때

    1. head에서 출발해서 끝까지 간다.
    2. 마지막 전 노드의 링크를 null로 설정한다.
    3. 마지막 노드는 지운다. (delete를 써도 되고 null로 설정해도 되고)

* list 중간을 삭제할때

    1. 삭제할 특정값을 찾아낸다.
    2. 이전 노드(이하 P)의 링크를 삭제할 노드의 링크로 설정한다.
    3. 삭제할 노드를  지운다.

<a href="/assets/Linked_List/3.PNG" data-lightbox="linkedlist1" data-title="출처: 그림">
    <img src="/assets/Linked_List/3.PNG" title="3">
</a>

### Boolean Isempty()

비었는지 확인하는 메소드. head가 null이면 true 아니면 false return.

## Linked Stack and Queue

이 부분은 따로 설명하지 않고, 이미지와 코드만 밑에 첨부하겠다.

<a href="/assets/Linked_List/4.PNG" data-lightbox="linkedlist1" data-title="출처: 그림">
    <img src="/assets/Linked_List/4.PNG" title="4">
</a>

# 4. 코드

* Linked List:
<https://github.com/21600055/DataStructures/blob/main/src/main/java/DataStructures/Linked_List.java>

* Linked Stack:
<https://github.com/21600055/DataStructures/blob/main/src/main/java/DataStructures/Linked_Stack.java>

* Linked Queue:

<https://github.com/21600055/DataStructures/blob/main/src/main/java/DataStructures/Linked_Queue.java>

개인적으로 정리한 자료구조입니다. 수정되거나 건의 할 사항이 있으면, <21600055@handong.edu>로 메일 바랍니다.
