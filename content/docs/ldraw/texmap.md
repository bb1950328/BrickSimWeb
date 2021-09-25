---
title: "!TEXMAP Language Extension"
weight: 1
---

{{< tip "warning" >}} This page contains my interpretation
of [the official LDraw document](https://www.ldraw.org/documentation/ldraw-org-file-format-standards/language-extension-for-texture-mapping.html). Information on this page may be wrong. {{< /tip >}}

[Official LDraw document](https://www.ldraw.org/documentation/ldraw-org-file-format-standards/language-extension-for-texture-mapping.html)

Line Syntax:
```ldr
0 !TEXMAP (START | NEXT) (PLANAR | CYLINDRICAL | SPHERICAL) x1 y1 z1 x2 y2 z2 x3 y3 z3 [a] [b] <pngfile> [GLOSSMAP pngfile]
0 !: <geometry1>
<geometry2>
0 !TEXMAP FALLBACK
<geometry3>
0 !TEXMAP END 
```

## Planar Mapping

{{< block "grid-2 mt-2" >}}
{{< column >}}
1. There are three points specified: `P1(x1, y1, z1)`, `P2(x2, y2, z2)` and `P3(x3, y3, z3)`.
   These points form a rectangle. (The standard does not explicitly say that `∠P2 P1 P3 = 90°` so they could also form a parallelogram.
   I don't know what to do in that case, maybe skew the image?)
2. The specified image file is drawn onto that rectangle. `P1` is the top-left, `P2` the top-right and `P3` the bottom-left corner.
   This image is shown here to explain the next steps, but not in the result.
3. Four [Lines](https://en.wikipedia.org/wiki/Line_(geometry)) that are perpendicular to the rectangle and go through its corners can be calculated.
   Only points between these lines will get textured.
4. The `<geometry1>` and `<geometry2>` sections contain geometry to which the texture is applied. 
   In this animation it's the [Blender Monkey](https://docs.blender.org/manual/en/latest/modeling/meshes/primitives.html#monkey).
5. If we want to know how a given point on the object is colored, we cast a ray that starts from the given point and is perpendicular to the rectangle.
   The color of the texture at the point where the ray meets the rectangle is taken.
6. The raycasting process is done for all points on the object. We can see that the texture is not mapped to the outer half of the monkey's ear.
   This is because the ray misses the texture there. In that case the color of the point is taken from the geometry line, as if there was no `!TEXMAP` at all.
{{< /column >}}
{{< column >}}
![Animation to explain planar mapping](../../../img/planarTexmap/animation.gif)
(Download the [.blend](../../../img/planarTexmap/planarTexmap.blend) or [the individual images](../../../img/planarTexmap/planarTexmapAnimationSingleFrames.zip))
{{< /column >}}
{{< /block >}}