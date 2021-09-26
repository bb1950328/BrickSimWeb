---
title: "!TEXMAP Language Extension"
weight: 1
---

{{< tip "warning" >}} This page contains my interpretation
of [the official LDraw document](https://www.ldraw.org/documentation/ldraw-org-file-format-standards/language-extension-for-texture-mapping.html). Information on this page may be wrong. {{< /tip >}}

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

## Cylindrical Mapping
{{< block "grid-2 mt-2" >}}
{{< column >}}
1. There are three points specified: `P1(x1, y1, z1)`, `P2(x2, y2, z2)` and `P3(x3, y3, z3)`.
   I think that `∠P2 P1 P3` should be `90°`, but that's not stated in the standard. `P1` and `P2` will form the radial axis (red line).
2. A part of a cylindrical surface is taken (blue). The angle is `a` and the middle is at `P3`. The radius equals to the distance between `P1` and `P3`.
3. The texture image is put onto that blue cylindrical plane. This image is only shown in the animation, it's not part of the result.
4. The object formed from the `<geometry1>` and `<geometry2>` lines usually is near `P1` and `P2`.
   But I think it also can be outside the blue plane. Only points between the black lines will get textured.
5. To find the color for a given point on the object, a ray has to be casted. It is perpendicular to the radial axis and goes through the given point.
   If the ray also goes through the image plane, the color of the given point is the color of the texture at the intersection point.
   If the ray misses the plane, the color of the given point is taken from the geometry line, as if there was no `!TEXMAP` at all.
6. When that process is done for all points on the object, the texture is cylindrically projected onto it.
{{< /column >}}
{{< column >}}
![Animation to explain cylindrical mapping](../../../img/cylindricalTexmap/animation.gif)
(Download the [.blend](../../../img/cylindricalTexmap/cylindricalTexmap.blend) or [the individual images](../../../img/cylindricalTexmap/cylindricalTexmapAnimationSingleImages.zip))
{{< /column >}}
{{< /block >}}

## Spherical mapping

{{< block "grid-2 mt-2" >}}
{{< column >}}
1. There are three points specified: `P1(x1, y1, z1)`, `P2(x2, y2, z2)` and `P3(x3, y3, z3)`.
   They form a plane (blue).
2. There also are two angles specified: `a` and `b`. Two [circular sector](https://en.wikipedia.org/wiki/Circular_sector) can be computed.
   The first one (purple) lies on the blue plane, has the angle `a`, the center at `P1` and the middle of the arc is at `P2`.
3. The second circle (orange) also has its center at `P1` and touches `P2` at the middle of its arc. It is perpendicular to the blue plane.
4. Together, these two circles form a spherical rectangle (blue).
5. Before we project our image onto our object, we project it onto that blue spherical rectangle.
6. For any point on the spherical rectangle we can calculate two angles (purple and orange), starting from `P2`.
7. These two angles are then mapped to the texture to get the color.
8. When this process is done for all points on the spherical rectangle, the texture is projected onto it.
9. The object formed from the `<geometry1>` and `<geometry2>` lines usually is near `P1`, but I think it also can be on the other side of the spherical rectangle.
   Only points inside the black lines will get textured. In this animation the object (green) is a part of a sphere with a dent.
10. Like with planar and cylindrical projection we can cast rays to get the color of a given point of the object. The ray starts at `P1` and goes through the given point.
11. If it intersects the spherical rectangle, the point on the object is colored like the texture on the spherical rectangle.
    Otherwise, the color of the given point is taken from the geometry line, as if there was no `!TEXMAP` at all.
12. If this process is executed for all points on the object, the texture gets applied to it.
{{< /column >}}
{{< column >}}
![Animation to explain spherical mapping](../../../img/sphericalTexmap/animation.gif)
(Download the [.blend](../../../img/sphericalTexmap/sphericalTexmap.blend) or [the individual images](../../../img/sphericalTexmap/sphericalTexmapAnimationSingleImages.zip))
{{< /column >}}
{{< /block >}}