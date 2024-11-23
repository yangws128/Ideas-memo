# mathematex

I hate shift, I hate using multiple curly brakets, but I like TEX..., and I also love functional programming
I just want to write mathematical equations easier, so I made this. 

## Grammar
words are tokens.  whitespaces counts once.

### 0. Functions

- `\func`
no-argument functions (which should not be called as functions) are regarded as text replacement...

- `\func[arg1;arg2; ...]`  
calls function with arguments

In math mode, especially,
- `arg2 \.func[arg1]` 
syntatic sugars for functions! 
	- `[5-x]\.div[3]` equals to $\frac{5-x}{3}$
	- `x\.func[y;z] = \func[x;y;z]`
- `[arg1 ; arg2 ; arg3]\foldr(foldl).func`
also a syntatic sugar for nested binary operators,
	- `[2;3;5;7]\right.pow` becomes $2^{3^{5^7}}$
	- `[2;3;5;7]\left.pow` becomes ${{2^3}^5}^7 = 2^{3\times 5 \times 7}$
- matrix: 
	``` 
	\b.bmat
	1 2 [3x+7] ;
	x y [z-5] ;
	\e.bmat
	``` 	
	becomes $$ \begin{bmatrix}
	1 &  2 & 3x+7 \\ x & y & z-5
	\end{bmatrix} $$
	
	
### 1. Plaintext Mode
- `\b.type_A` => begins [type A] block
- `\e.type_A` => ends [type A] block
- <code>\` [math] \`</code> => inline math equation
	- tex-displaystyle is accepted by default...
- `\eq [block_eqns] \eq` => block-type math equation
- `\n` => really makes new line! (enters are regarded as whitespace)
### 2. Math mode
- `[somethings ... ]` => creates block (if without semicolons!)
- `[a ; b ; c]` => becomes list!
	- and inside `[ ]`, only ";" becomes argument delimiter, which means any expressions are regarded as blocks. (but still, you could create blocks manually inside a list like: `[a; [bx -c]; d]`)
- Because I hate "SHIFT" key, changed some mappings...
	- `k\.4`   $\quad\quad k_4$
	- `x\'2`  $\quad \quad x^2$
	- `\l \br \cl \vert \vvert ` $\quad \quad ( \quad ] \quad$ { $\quad  \vert \quad \Vert$
	- `\larrow \llarrow \lrarrow \lraarrow`  $\quad \quad \leftarrow \quad \Leftarrow \quad \leftrightarrow \quad \Leftrightarrow$
	- under and over text: `\uo[f;under;over]`
		- in example  `\sum\.uo[k=1;n\.pow[2]] f(k)` = $\displaystyle \sum_{k=1}^{n^2} f(k)$ 
- elsewhere, most of tex commands are usable


## Plans

I think, only minimal things will be implemented... to write just an informal reports!

### Default Fonts
Korean font: 마루 부리 (Naver)
English font: 마루 부리 (Naver)
Math font: DejavuMath (Google)

### Architecture
Plaintext -[JIT Compile]-> SVG -[Page Mapping]-> PDF
SVG Element Management: Raphael.js

## Ideas
If you have good ideas, plz give me some...

#### Placing the element [text-math]
1. Compile math objects first.
2. Get the bounding box of the math objects
3. Set line-height and math object offset
4. Draw!

#### Placing elements inside math
Deepest Object first...
