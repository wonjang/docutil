A ReStructuredText Primer
=========================

:Author: Richard Jones
:Version: $Revision: 5801 $
:Copyright: This document has been placed in the public domain.

.. contents::


다음 문서에는 링크가 포함 되어있습니다 "(quickref__)".  그 
링크들은 상대주소로 user reference 와 링크 되어있습니다 `Quick reStructuredText`_.
만약 이 링크들이 끊어졌다면 , 직접 `master
quick reference`_ 문서를 참고하면 됩니다.

__
.. _Quick reStructuredText: quickref.html
.. _master quick reference:
   http://docutils.sourceforge.net/docs/user/rst/quickref.html

.. Note:: 이 문서는 간단하게 reStructuredText 를 소개합니다.
   `What Next?`_ 아래에 있는 섹션을 참고하면 보다 많은
   자료와 정보를 포함한 정식 문서가 링크되어있다.


Structure
---------

시작부터 "Structured Text"에 대하여 언급하는 것은 아마도 조금
애매한 부분이 있다. 그것은 "Relaxed Text" 라고하는 확실하고 
한결같은 패턴을 사용한다.  이 패턴들은 HTML 번역기에 의해 해석되어져서
"Very Structured Text" 문서를 생성하고 그것은 웹브라우져에서 
사용된다.

가장 기본적인 패턴을 인식하는 것은 **paragraph** (quickref__) 이다.
그것은 빈줄로 구분 되어지는 글자의 덩어리이다(한줄 이면 
충분하다).  Paragraphs 반드시 들여쓰기 수준이 같다 -- 즉, 줄시작 지점에서
문서의 왼쪽끝까지를 말한다.  Paragraphs 에서 들여쓰기를 시작하는 규칙은
다음과 같다. 예를 들어::

  This is a paragraph.  It's quite
  short.

     This paragraph will result in an indented block of
     text, typically used for quoting other text.

  This is another one.

결과 :

  This is a paragraph.  It's quite
  short.

     This paragraph will result in an indented block of
     text, typically used for quoting other text.

  This is another one.

__ quickref.html#paragraphs


Text styles
-----------

(quickref__)

__ quickref.html#inline-markup

paragraphs 이나 다른 문서속에서 *italics* "``*italics*``" 나 **bold** 
"``**bold**``" 를 표현 할 수 있다 이것을 "inline markup" 이라한다.

만약 고정된 공간을 표현하고 싶으면 "````double back-quotes````"
위와 같이 '' ''  을 사용해서 표현하면 된다. '' '' 안쪽에는 * 등 특수 문자를 사용 할 수 있다.

특수한 문자를 나타내려고 하면 -- reStructuredText 는 상당히 잘 표현 된다.
예를 들어 * 한개 혹은 5*6= 30 과 같은 수식 모두 표현 된다.
만약 * 로 둘러 싸여 있지만 이탤릭체로 표현하지 않으려면 '' '' 을 사용하거나 \* 를 사용하면 
된다. "``\*``", 즉::

   ``*``
 
__ quickref.html#escaping

.. Tip:: inline markup 을 parentheses의 형태로 사용하려면 마크업될 글자의 바로 앞뒤에 존재해댜한다.
   Inline markup 공백으로 둘러쌓여 있거나 단어 중간에 있는 것들은 markup으로 인식되지 않는다.
   markup spec  보면 상세한내용이 있다.

__ ../../ref/rst/restructuredtext.html#inline-markup


Lists
-----

세가지 형태의 리스트가 존재한다 : **enumerated**,
**bulleted** 그리고 **definitions**. 모든 리스트에서 paragraphs와 sublists등을 모두 사용할 수 있다.
리스트를 사용하기 원한다면 문장의 첫줄이나 paragraph 왼쪽 편이 정렬만 되면 된다.

그리고 리스트는 새로운 paragraph으로 시작해야한다.  -- 즉, 반드시 빈줄 다음에 나와야 한다.

**enumerated** lists (numbers, letters or roman numerals; quickref__)
  __ quickref.html#enumerated-lists

  Start a line off with a number or letter followed by a period ".",
  right bracket ")" or surrounded by brackets "( )" -- whatever you're
  comfortable with.  All of the following forms are recognised::

    1. numbers

    A. upper-case letters
       and it goes over many lines

       with two paragraphs and all!

    a. lower-case letters

       3. with a sub-list starting at a different number
       4. make sure the numbers are in the correct sequence though!

    I. upper-case roman numerals

    i. lower-case roman numerals

    (1) numbers again

    1) and again

  결과 (알림 : 모든 웹브라우저에서 enumerated list styles 를 지원하지 않는다. 
  그래서 모든 효과를 표현 할 수 없다):

  1. numbers

  A. upper-case letters
     and it goes over many lines

     with two paragraphs and all!

  a. lower-case letters

     3. with a sub-list starting at a different number
     4. make sure the numbers are in the correct sequence though!

  I. upper-case roman numerals

  i. lower-case roman numerals

  (1) numbers again

  1) and again

**bulleted** lists (quickref__)
  __ quickref.html#bullet-lists

  enumerated lists와 비슷한데  "-", "+" 나 "*" 등으로 구분한다::
    * a bullet point using "*"

      - a sub-list using "-"

        + yet another sub-list

      - another item

  결과:

  * a bullet point using "*"

    - a sub-list using "-"

      + yet another sub-list

    - another item

**definition** lists (quickref__)
  __ quickref.html#definition-lists

  위에 있는 두가지 형태의 리스트와는 달리 형태가 아래와 같다::

    what
      Definition lists associate a term with a definition.

    *how*
      The term is a one-line phrase, and the definition is one or more
      paragraphs or body elements, indented relative to the term.
      Blank lines are not allowed between term and definition.

  결과:

  what
    Definition lists associate a term with a definition.

  *how*
    The term is a one-line phrase, and the definition is one or more
    paragraphs or body elements, indented relative to the term.
    Blank lines are not allowed between term and definition.


Preformatting (code samples)
----------------------------
(quickref__)

__ quickref.html#literal-blocks

전처리된 것들을 포함시키려면 앞 paragraph 이 끝나는 부분에 "``::``" 를 함께 둔다.
전처리된 블록이 동일한 들여쓰기 수준으로 돌아가면 블록이 완료되고, 
들여쓰기 수준으로 미리 서식이 지정된 블록보다 먼저 paragraph 으로 나타내어집니다. For example::

  An example::

      Whitespace, newlines, blank lines, and all kinds of markup
        (like *this* or \this) is preserved by literal blocks.
    Lookie here, I've dropped an indentation level
    (but not far enough)

  no more example

결과:

  An example::

      Whitespace, newlines, blank lines, and all kinds of markup
        (like *this* or \this) is preserved by literal blocks.
    Lookie here, I've dropped an indentation level
    (but not far enough)

  no more example

만약 paragraph 이  "``::``", 으로만 되어있으면 제거됩니다.
from the output::

  ::

      This is preformatted text, and the
      last "::" paragraph is removed

결과:

::

    This is preformatted text, and the
    last "::" paragraph is removed


Sections
--------

(quickref__)

__ quickref.html#section-structure

긴 문자를 나누려면  **section headers** 를 사용하면 된다.
이건 한줄(한 단어 이상)의 문자입니다. 그 문자는 이런 것들로 꾸며집니다. : 
아랫줄만 , 혹은 위아래 같이 , 줄모양 "``-----``", 이나 등호 "``======``", 물결 "``~~~~~~``"
이나 다른 어떤 문자혹은 숫자가 아닌 다음과 같은 당신이 편하게 생각하는 특수문자들 ``= - ` : ' " ~ ^ _ * + # < >``
아랫줄만 사용하는 것이랑 위 아래 모두 사용하는 경우는 다른 경우로 구분 됩니다.
아랫줄이나 윗줄 아랫줄 같이쓰는 경우 모두  함께 쓰이는 문자보다 길어야 합니다. 
동일한 장식형태로 되어있는 부분은 모두 같은 수준이 됩니다.::

  Chapter 1 Title
  ===============

  Section 1.1 Title
  -----------------

  Subsection 1.1.1 Title
  ~~~~~~~~~~~~~~~~~~~~~~

  Section 1.2 Title
  -----------------

  Chapter 2 Title
  ===============

결과는 다음과 같이 됩니다. 다음은 의사 XML코드로 나타낸 것입니다.
pseudo-XML::

    <section>
        <title>
            Chapter 1 Title
        <section>
            <title>
                Section 1.1 Title
            <section>
                <title>
                    Subsection 1.1.1 Title
        <section>
            <title>
                Section 1.2 Title
    <section>
        <title>
            Chapter 2 Title

(의사 XML 코드는 중첩된 들여쓰기 규칙을 사용하며 끝나는 태그가 없습니다.
태그사이에 블록에 ""이 들어갈 수 없기때문데 다른 것들은 실제로 출력하는 것이 불가능합니다.
구체적으로 확인하려면 이 부분의 실제 소스코드와 출력을 비교하면 됩니다.)

섹션의 헤더는 해당 이름으로 링크의 대상으로 사용할 수 있다. 그 해당 링크로 연결하기 위해서
"``Lists_``"  Lists_ 라 씁니다. 만약 이름에 공백이 있다면 ''로 묶어서 "```text styles`_``" `text styles`_
표현하면 됩니다.


Document Title / Subtitle
`````````````````````````

전체 문서의 제목은 섹션제목과 다른 형식들과 다릅니다.
(예 HTML 생성기가 디폴트로 제목을 중앙에 정렬할수 있습니다.)

reStructuredText 에 문서제목을 나타내려면 유니크한 장식스타일을 사용하면 됩니다. 
부 제목을 나타내고 싶으면 바로 뒤에 다른 장식프타일을 사용해서 작성하면 됩니다.
For example::

    ================
     Document Title
    ================
    ----------
     Subtitle
    ----------

    Section Title
    =============

    ...

보기에 주제목과 섹션 제목이 같은 스타일로 장식된것으로 보이지만 한개는 아랫줄만 
한개는 위아래로 나타내져 있기 때문에 둘이 다릅니다.



Images
------

(quickref__)

__ quickref.html#directives

문서에 이미지를 포함시키려면 이미지 지사자를 사용하변 됩니다 ``image`` directive__.
For example::

  .. image:: images/biohazard.png

결과:

.. image:: images/biohazard.png

``images/biohazard.png`` 만약 파일에 추가정보(형식, 크기 등)을 나타내고 
싶으면 다음과 같이 하면 됩니다.::

  .. image:: images/biohazard.png
     :height: 100
     :width: 200
     :scale: 50
     :alt: alternate text

자세한 정보는 `image directive documentation`__ 를 참고.

__ ../../ref/rst/directives.html
__ ../../ref/rst/directives.html#images


What Next?
----------

이 입문서는 대략적으로 reStructuredText 일반 적인 것들을 소개했지만 앞으로 볼것이 더 많습니다.
더 많은 정보를 원하면 다음 링크를 참고.  The `Quick reStructuredText`_
더 상세한 내용을 알고 싶으면 다음 링크를 참고.`reStructuredText Markup Specification`_ 
직접 레퍼런스 확인하기 [#]_.

Docutils or reStructuredText 더 도움이 필요하다면 Docutils-users mailing list 에 
메세지를 보내실 수 있습니다. 


.. [#] 링크가 동작하지 않으면 직접 접근하면 됩니다:
   http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html.

.. _reStructuredText Markup Specification:
   ../../ref/rst/restructuredtext.html
.. _Docutils-users: ../mailing-lists.html#docutils-users
.. _Docutils project web site: http://docutils.sourceforge.net/