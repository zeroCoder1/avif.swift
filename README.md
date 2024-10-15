# avif.swift

## What's This?
Introducing AVIF.swift, the ultimate image decoding solution for AVIF images on iOS and macOS. The AVIFDecoder.decode method allows you to easily read and write AVIF images using the power of Swift. With AVIF.swift, you can decode AVIF images with up to 50% smaller file sizes and 25% better compression than JPEG, all while maintaining the highest quality. This package is compatible with both Swift Package Manager and CocoaPods. Try AVIF.swift today and see the difference for yourself. Check it out at https://github.com/awxkee/avif.swift

This package is provides full (compatibility support) for AVIF images for all apple platforms. Supports encode AVIF and decode AVIF images in convinient and fast way


Package based on `dav1d` to have the best speed of decompressing on devices that do not have support for AV1 hardware codec.
As AVIF encoder have `aom` as just this one looks reasonable to encode AVIF images on mobile devices
</br>
Main aim of the project is to use `AVIF` image on all Apple platforms etc with usable speed and convenience

Supports animated AVIF's with realtime FPS like 24+
Also supports encoding animated AVIF's

Handles HDR images with PQ, HLG and SMPTE428 transfer functions

Precompiled for iOS 11+, Mac OS 12+, Mac Catalyst 14+, WatchOS 6+, tvOS 13+

## Installation

### [Swift Package Manager](https://swift.org/package-manager/)

Go to `File / Swift Packages / Add Package Dependency…`
and enter package repository URL https://github.com/awxkee/avif.swift.git, then select the latest master branch
at the time of writing.

## Usage

```swift
import avif
// Decompress data
let uiImage: UIImage? = AVIFDecoder.decode(Data(), sampleSize: .zero) // or any max CGSize of image
// Compress
let data: Data = try AVIFEncoder().encode(image: UIImage())

// Decode animated
let animatedDecoder = AnimatedDecoder(withData: Data())
let frame: CGImage = try animatedDecoder.get(frame: 1)
let image: UIImage = try animatedDecoder.getImage(frame: 1) 

// Encode animation
import avifc

let animatedEncoder = AVIFAnimatedEncoder()
animatedEncoder.create()
try animatedEncoder.addImage(UIImage(), duration: 250)
let encodedData = animatedEncoder.encode()
```

## Disclaimer

#AVIF
Alliance for Open Media has developed the AVIF image format, a format that makes images have a smaller file size than with JPEG, PNG, GIF, or HEIF, without sacrificing image quality. AVIF offers lossy and lossless compression and has already 70% support by web browsers. It is regarded as a significant advancement in media compression. It is the goal of AOMedia to create open, royalty-free software standards for multimedia distribution. Specifically, AVIF will be free for everyone to use. There is a long list of big companies behind AOMedia, including Netflix, Google, Facebook, Apple, and Microsoft. In terms of image file formats for the web, JPG and PNG are considered the most popular. Several years ago, Google developed a format called WebP that delivers images 30% smaller than JPGs, while maintaining image quality. With AVIF, images are 50% smaller than JPG while maintaining the same quality.

## TODO
- [ ] Tests
- [ ] Some examples 
