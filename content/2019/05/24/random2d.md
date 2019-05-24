## Seeded Random 2D Point

Here's a quick [Amplify Shader Editor](https://assetstore.unity.com/packages/tools/visual-scripting/amplify-shader-editor-68570) function to give you a seeded random 2D point between (0,0) and (1,1)!

[Download](./Random%202D%20Point.asset)

How it works:

1. Accept `Seed`, `X Offset`, and `Y Offset` parameters, all optional
1. Add `Seed + X Offset` and `Seed + Y Offset` to get floats `x` and `y`
1. Feed two vector2s, `(x,x)` and `(y,y)` into two simplex2d noise functions
    1. A 2d noise function will take a vector2 as an input and output a pseudorandom float between -1 and 1 - see [The Book of Shaders](https://thebookofshaders.com/11/) for more info
1. Append the results of the two noise functions to a new vector2 `v`, which will be between (-1,-1) and (1,1)
1. [Scale and Offset](http://wiki.amplify.pt/index.php?title=Unity_Products:Amplify_Shader_Editor/Scale_And_Offset) `v` to bring it into the range (0,0) to (1,1)
1. Output the result!

This is a really useful tool that we'll tap into later on to create some seeded Voronoi diagrams, using outputs from this function as the cell centerpoints.
