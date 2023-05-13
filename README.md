# solacon for Kotlin Android

Full credit to [naknomum](https://github.com/naknomum/solacon) who created the original JS version.  I just converted it to
java with a little AI assistance.

# solacon

A *solacon* is a variation of an [identicon](https://en.wikipedia.org/wiki/Identicon), in the form of a solar/spiral/floral shape.
This is also known as a "visual hash".

The solacon is **seeded with a value** (string) which determines the shape, symmetry, and shades of the image.

The SVG file contains all the javascript needed to generate the content, so one only needs to set attributes (e.g. `data-value`) on the object
that is embedding the svg.

![Solacon.svg](Solacon.svg.png "Solacon.svg")

## Example

Original javascript demo:
Try out some [dynamical examples](https://naknomum.github.io/solacon-example/) of **solacons** in action.

Java implementation looks identical


## Usage

```Kotlin
val solaconGenerator = Solacon()

solacon = view.findViewById(R.id.solacon)
solacon.setOnClickListener { view ->
    val hash = java.util.UUID.randomUUID().toString()
    val size = 512 // desired size of the identicon in pixels
    //3rd parameter is an optional color, must be formatted: "#XXXXXX"
    val solaconBitmap = solaconGenerator.generateBitmap(hash, size)
    solacon.setImageBitmap(solaconBitmap)
}
solacon.performClick()
```

## Similar projects

For related work, check out [Awesome Identicons](https://github.com/drhus/awesome-identicons), a curated list of _visual hashes_ maintained by **Husam ABBOUD**.

