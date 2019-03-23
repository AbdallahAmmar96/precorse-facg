# CSS Specificity
When more than one set of CSS rules apply to the same element, the browser will have to decide which specific set will be applied to the element. The rules the browser follows are collectively called **Specificity**

## Specificity Rules include:

**Inline CSS>Internal CSS>External CSS**

- CSS style applied by referencing external stylesheet has lowest precedence and is overridden by Internal and inline CSS.
- Internal CSS is overridden by inline CSS.
- Inline CSS has highest priority and overrides all other selectors.

Example :
[Specificity Rules Example](https://codepen.io/aminalakhsham/pen/VRgpXd).

## Specificity Hierarchy
**Specificity Hierarchy :** Every element selector has a position in the Hierarchy.

- Inline style: Inline style has highest priority.
- Identifiers(ID): ID have the second highest priority.
- Classes, pseudo-classes and attributes: Classes, pseudo-classes and attributes are come next.
- Elements and pseudo-elements: Elements and pseudo-elements have lowest priority.

**Note:**
- When two or more selectors have equal specificity, the last(latest) one counts.
- Universal selectors like body and inherited selectors have least specificity.

Example :
[Specificity Hierarchy Example](https://codepen.io/aminalakhsham/pen/oVmZMd?editors=1100).

## How to Calculate Specificity?
Start at 0, add 1000 for style attribute(inline CSS), add 100 for each ID, add 10 for each attribute, class or pseudo-class, add 1 for each element name.

Example :
[Calculate Specificity Example](https://codepen.io/aminalakhsham/pen/BbMWGX)

![Calculate Specificity](https://specifishity.com/specifishity.png)

## The :not() exception :

The :not() CSS pseudo-class represents elements that do not match a list of selectors. Since it prevents specific items from being selected, it is known as the negation pseudo-class.

Example :
[not exception Example](https://codepen.io/aminalakhsham/pen/Oqdpde)
