<div align=center>
<a href="https://uvdream.github.io/lancet-docs/en/"><img src="./logo.png" width="200" height="200"/></a>

<br/>

![Go version](https://img.shields.io/badge/go-%3E%3Dv1.18-9cf)
[![Release](https://img.shields.io/badge/release-2.1.12-green.svg)](https://github.com/duke-git/lancet/releases)
[![GoDoc](https://godoc.org/github.com/duke-git/lancet/v2?status.svg)](https://pkg.go.dev/github.com/duke-git/lancet/v2)
[![Go Report Card](https://goreportcard.com/badge/github.com/duke-git/lancet/v2)](https://goreportcard.com/report/github.com/duke-git/lancet/v2)
[![test](https://github.com/duke-git/lancet/actions/workflows/codecov.yml/badge.svg?branch=main&event=push)](https://github.com/duke-git/lancet/actions/workflows/codecov.yml)
[![codecov](https://codecov.io/gh/duke-git/lancet/branch/main/graph/badge.svg?token=FC48T1F078)](https://codecov.io/gh/duke-git/lancet)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/duke-git/lancet/blob/main/LICENSE)

</div>

<div STYLE="page-break-after: always;"></div>

<p style="font-size: 20px"> 
    Lancet is a comprehensive, efficient, and reusable util function library of go. Inspired by the java apache common package and lodash.js.
</p>

English | [简体中文](./README_zh-CN.md)

## Feature

-   👏 Comprehensive, efficient and reusable.
-   💪 300+ go util functions, support string, slice, datetime, net, crypt...
-   💅 Only depend on the go standard library.
-   🌍 Unit test for every exported function.

## Installation

### Note:

1. <b>For users who use go1.18 and above, it is recommended to install lancet v2.x.x. Cause in v2.x.x all functions was rewriten with generics of go1.18.</b>

```go
go get github.com/duke-git/lancet/v2 // will install latest version of v2.x.x
```

2. <b>For users who use version below go1.18, you should install v1.x.x. The latest of v1.x.x is v1.3.5. </b>

```go
go get github.com/duke-git/lancet@v1.3.5 // below go1.18, install latest version of v1.x.x
```

## Usage

Lancet organizes the code into package structure, and you need to import the corresponding package name when use it. For example, if you use string-related functions,import the strutil package like below:

```go
import "github.com/duke-git/lancet/v2/strutil"
```

## Example

Here takes the string function Reverse (reverse order string) as an example, and the strutil package needs to be imported.

```go
package main

import (
    "fmt"
    "github.com/duke-git/lancet/v2/strutil"
)

func main() {
    s := "hello"
    rs := strutil.Reverse(s)
    fmt.Println(rs) //olleh
}
```

## Documentation

### 1. Algorithm package implements some basic algorithm. eg. sort, search.

```go
import "github.com/duke-git/lancet/v2/algorithm"
```

#### Function list:

-   **<big>BubbleSort</big>** : sorts slice with bubble sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#BubbleSort)]
    [[play](https://go.dev/play/p/GNdv7Jg2Taj)]
-   **<big>CountSort</big>** : sorts slice with bubble sort algorithm, don't change original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#CountSort)]
    [[play](https://go.dev/play/p/tB-Umgm0DrP)]
-   **<big>HeapSort</big>** : sorts slice with heap sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#HeapSort)]
    [[play](https://go.dev/play/p/u6Iwa1VZS_f)]
-   **<big>InsertionSort</big>** : sorts slice with insertion sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#InsertionSort)]
    [[play](https://go.dev/play/p/G5LJiWgJJW6)]
-   **<big>MergeSort</big>** : sorts slice with merge sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#MergeSort)]
    [[play](https://go.dev/play/p/ydinn9YzUJn)]
-   **<big>QuickSort</big>** : sorts slice with quick sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#QuickSort)]
    [[play](https://go.dev/play/p/7Y7c1Elk3ax)]
-   **<big>SelectionSort</big>** : sorts slice with selection sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#SelectionSort)]
    [[play](https://go.dev/play/p/oXovbkekayS)]
-   **<big>ShellSort</big>** : sorts slice with shell sort algorithm, will change the original slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#ShellSort)]
    [[play](https://go.dev/play/p/3ibkszpJEu3)]
-   **<big>BinarySearch</big>** : returns the index of target within a sorted slice, use binary search (recursive call itself).
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#BinarySearch)]
    [[play](https://go.dev/play/p/t6MeGiUSN47)]
-   **<big>BinaryIterativeSearch</big>** : returns the index of target within a sorted slice, use binary search (no recursive).
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#BinaryIterativeSearch)]
    [[play](https://go.dev/play/p/Anozfr8ZLH3)]
-   **<big>LinearSearch</big>** : returns the index of target in slice base on equal function.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#LinearSearch)]
-   **<big>LRUCache</big>** : implements memory cache with lru algorithm.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/algorithm.md#LRUCache)]
    [[play](https://go.dev/play/p/-EZjgOURufP)]

### 2. Concurrency package contain some functions to support concurrent programming. eg, goroutine, channel, async.

```go
import "github.com/duke-git/lancet/v2/concurrency"
```

#### Function list:

-   **<big>NewChannel</big>** : create a Channel pointer instance.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#NewChannel)]
-   **<big>Bridge</big>** : link multiply channels into one channel.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/Bridge.md#NewChannel)]
-   **<big>FanIn</big>** : merge multiple channels into one channel.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#FanIn)]
-   **<big>Generate</big>** : creates a channel, then put values into the channel.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#Generate)]
-   **<big>Or</big>** : read one or more channels into one channel, will close when any readin channel is closed.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#Or)]
-   **<big>OrDone</big>** : read a channel into another channel, will close until cancel context.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#OrDone)]
-   **<big>Repeat</big>** : create channel, put values into the channel repeatly until cancel the context.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#Repeat)]
-   **<big>RepeatFn</big>** : create a channel, excutes fn repeatly, and put the result into the channel, until close context.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#RepeatFn)]
-   **<big>Take</big>** : create a channel whose values are taken from another channel with limit number.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#Take)]
-   **<big>Tee</big>** : split one chanel into two channels, until cancel the context.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/concurrency.md#Tee)]

### 3. Condition package contains some functions for conditional judgment. eg. And, Or, TernaryOperator...

```go
import "github.com/duke-git/lancet/v2/condition"
```

#### Function list:

-   **<big>Bool</big>** : returns the truthy value of anything.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#Bool)]
    [[play](https://go.dev/play/p/ETzeDJRSvhm)]
-   **<big>And</big>** : returns true if both a and b are truthy.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#And)]
    [[play](https://go.dev/play/p/W1SSUmt6pvr)]
-   **<big>Or</big>** : returns false if neither a nor b is truthy.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#Or)]
    [[play](https://go.dev/play/p/UlQTxHaeEkq)]
-   **<big>Xor</big>** : returns true if a or b but not both is truthy.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#Xor)]
    [[play](https://go.dev/play/p/gObZrW7ZbG8)]
-   **<big>Nor</big>** : returns true if neither a nor b is truthy.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#Nor)]
    [[play](https://go.dev/play/p/g2j08F_zZky)
-   **<big>Xnor</big>** : returns true if both a and b or neither a nor b are truthy.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#Xnor)]
    [[play](https://go.dev/play/p/OuDB9g51643)]
-   **<big>Nand</big>** : returns false if both a and b are truthy.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#Nand)]
    [[play](https://go.dev/play/p/vSRMLxLIbq8)]
-   **<big>TernaryOperator</big>** : ternary operator.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/condition.md#TernaryOperator)]
    [[play](https://go.dev/play/p/ElllPZY0guT)]

### 4. Convertor package contains some functions for data convertion.

```go
import "github.com/duke-git/lancet/v2/convertor"
```

#### Function list:

-   **<big>ColorHexToRGB</big>** : convert color hex to color rgb.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ColorHexToRGB)]
    [[play](https://go.dev/play/p/o7_ft-JCJBV)]
-   **<big>ColorRGBToHex</big>** : convert rgb color to hex color.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ColorRGBToHex)]
    [[play](https://go.dev/play/p/nzKS2Ro87J1)]
-   **<big>ToBool</big>** : convert string to bool.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToBool)]
    [[play](https://go.dev/play/p/ARht2WnGdIN)]
-   **<big>ToBytes</big>** : convert value to byte slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToBytes)]
    [[play](https://go.dev/play/p/fAMXYFDvOvr)]
-   **<big>ToChar</big>** : convert string to char slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToChar)]
    [[play](https://go.dev/play/p/JJ1SvbFkVdM)]
-   **<big>ToChannel</big>** : convert a collection of elements to a read-only channel.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToChannel)]
    [[play](https://go.dev/play/p/hOx_oYZbAnL)]
-   **<big>ToFloat</big>** : convert value to float64, if param is a invalid floatable, will return 0.0 and error.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToFloat)]
    [[play](https://go.dev/play/p/4YTmPCibqHJ)]
-   **<big>ToInt</big>** : convert value to int64 value, if input is not numerical, return 0 and error.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToInt)]
    [[play](https://go.dev/play/p/9_h9vIt-QZ_b)]
-   **<big>ToJson</big>** : convert value to a json string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToJson)]
    [[play](https://go.dev/play/p/2rLIkMmXWvR)]
-   **<big>ToMap</big>** : convert a slice of structs to a map based on iteratee function.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToMap)]
    [[play](https://go.dev/play/p/tVFy7E-t24l)]
-   **<big>ToPointer</big>** : return a pointer of passed value.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToPointer)]
    [[play](https://go.dev/play/p/ASf_etHNlw1)]
-   **<big>ToString</big>** : convert value to string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#ToString)]
    [[play](https://go.dev/play/p/nF1zOOslpQq)]
-   **<big>StructToMap</big>** : convert struct to map, only convert exported struct field.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#StructToMap)]
    [[play](https://go.dev/play/p/KYGYJqNUBOI)]
-   **<big>MapToSlice</big>** : convert map to slice based on iteratee function.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#MapToSlice)]
    [[play](https://go.dev/play/p/dmX4Ix5V6Wl)]
-   **<big>EncodeByte</big>** : encode data to byte slice.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#EncodeByte)]
    [[play](https://go.dev/play/p/DVmM1G5JfuP)]
-   **<big>DecodeByte</big>** : decode byte slice data to target object.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/convertor.md#DecodeByte)]
    [[play](https://go.dev/play/p/zI6xsmuQRbn)]

### 5. Cryptor package is for data encryption and decryption.

```go
import "github.com/duke-git/lancet/v2/cryptor"
```

#### Function list:

-   [AesEcbEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesEcbEncrypt)
-   [AesEcbDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesEcbDecrypt)
-   [AesCbcEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesCbcEncrypt)
-   [AesCbcDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesCbcDecrypt)
-   [AesCtrCrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesCtrCrypt)
-   [AesCfbEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesCfbEncrypt)
-   [AesCfbDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesCfbDecrypt)
-   [AesOfbEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesOfbEncrypt)
-   [AesOfbDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#AesOfbDecrypt)
-   [Base64StdEncode](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Base64StdEncode)
-   [Base64StdDecode](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Base64StdDecode)
-   [DesEcbEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesEcbEncrypt)
-   [DesEcbDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesEcbDecrypt)
-   [DesCbcEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesCbcEncrypt)
-   [DesCbcDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesCbcDecrypt)
-   [DesCtrCrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesCtrCrypt)
-   [DesCfbEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesCfbEncrypt)
-   [DesCfbDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesCfbDecrypt)
-   [DesOfbEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesOfbEncrypt)
-   [DesOfbDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#DesOfbDecrypt)
-   [HmacMd5](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#HmacMd5)
-   [HmacSha1](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#HmacSha1)
-   [HmacSha256](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#HmacSha256)
-   [HmacSha512](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#HmacSha512)
-   [Md5String](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Md5String)
-   [Md5File](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Md5File)
-   [Sha1](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Sha1)
-   [Sha256](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Sha256)
-   [Sha512](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#Sha512)
-   [GenerateRsaKey](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#GenerateRsaKey)
-   [RsaEncrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#RsaEncrypt)
-   [RsaDecrypt](https://github.com/duke-git/lancet/blob/main/docs/cryptor.md#RsaDecrypt)

### 6. Datetime package supports date and time format and compare.

```go
import "github.com/duke-git/lancet/v2/datetime"
```

#### Function list:

-   [AddDay](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#AddDay)
-   [AddHour](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#AddHour)
-   [AddMinute](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#AddMinute)
-   [BeginOfMinute](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#BeginOfMinute)
-   [BeginOfHour](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#BeginOfHour)
-   [BeginOfDay](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#BeginOfDay)
-   [BeginOfWeek](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#BeginOfWeek)
-   [BeginOfMonth](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#BeginOfMonth)
-   [BeginOfYear](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#BeginOfYear)
-   [EndOfMinute](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#EndOfMinute)
-   [EndOfHour](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#EndOfHour)
-   [EndOfDay](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#EndOfDay)
-   [EndOfWeek](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#EndOfWeek)
-   [EndOfMonth](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#EndOfMonth)
-   [EndOfYear](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#EndOfYear)
-   [GetNowDate](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#GetNowDate)
-   [GetNowTime](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#GetNowTime)
-   [GetNowDateTime](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#GetNowDateTime)
-   [GetZeroHourTimestamp](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#GetZeroHourTimestamp)
-   [GetNightTimestamp](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#GetNightTimestamp)
-   [FormatTimeToStr](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#FormatTimeToStr)
-   [FormatStrToTime](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#FormatStrToTime)
-   [NewUnix](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#NewUnix)
-   [NewUnixNow](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#NewUnixNow)
-   [NewFormat](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#NewFormat)
-   [NewISO8601](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#NewISO8601)
-   [ToUnix](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#ToUnix)
-   [ToFormat](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#ToFormat)
-   [ToFormatForTpl](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#ToFormatForTpl)
-   [ToIso8601](https://github.com/duke-git/lancet/blob/main/docs/datetime.md#ToIso8601)

### 7. Datastructure package constains some common data structure. eg. list, linklist, stack, queue, set, tree, graph.

```go
import list "github.com/duke-git/lancet/v2/datastructure/list"
import link "github.com/duke-git/lancet/v2/datastructure/link"
import stack "github.com/duke-git/lancet/v2/datastructure/stack"
import queue "github.com/duke-git/lancet/v2/datastructure/queue"
import set "github.com/duke-git/lancet/v2/datastructure/set"
import tree "github.com/duke-git/lancet/v2/datastructure/tree"
import heap "github.com/duke-git/lancet/v2/datastructure/heap"
import hashmap "github.com/duke-git/lancet/v2/datastructure/hashmap"
```

#### Function list:

-   [List](https://github.com/duke-git/lancet/blob/main/docs/datastructure/list.md)
-   [Linklist](https://github.com/duke-git/lancet/blob/main/docs/datastructure/linklist.md)
-   [Stack](https://github.com/duke-git/lancet/blob/main/docs/datastructure/stack.md)
-   [Queue](https://github.com/duke-git/lancet/blob/main/docs/datastructure/queue.md)
-   [Set](https://github.com/duke-git/lancet/blob/main/docs/datastructure/set.md)
-   [Tree](https://github.com/duke-git/lancet/blob/main/docs/datastructure/tree.md)
-   [Heap](https://github.com/duke-git/lancet/blob/main/docs/datastructure/heap.md)
-   [HashMap](https://github.com/duke-git/lancet/blob/main/docs/datastructure/hashmap.md)

### 8. Fileutil package implements some basic functions for file operations.

```go
import "github.com/duke-git/lancet/v2/fileutil"
```

#### Function list：

-   **<big>ClearFile</big>** : write empty string to target file.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#ClearFile)]
    [[play](https://go.dev/play/p/NRZ0ZT-G94H)]
-   **<big>CreateFile</big>** : create file in path.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#CreateFile)]
    [[play](https://go.dev/play/p/lDt8PEsTNKI)]
-   **<big>CreateDir</big>** : create directory in absolute path.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#CreateDir)]
    [[play](https://go.dev/play/p/qUuCe1OGQnM)]
-   **<big>CopyFile</big>** :copy src file to dest file.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#CopyFile)]
    [[play](https://go.dev/play/p/Jg9AMJMLrJi)]
-   **<big>FileMode</big>** : return file's mode and permission.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#FileMode)]
    [[play](https://go.dev/play/p/2l2hI42fA3p)]
-   **<big>MiMeType</big>** : return file mime type.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#MiMeType)]
    [[play](https://go.dev/play/p/bd5sevSUZNu)]
-   **<big>IsExist</big>** : checks if a file or directory exists.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#IsExist)]
    [[play](https://go.dev/play/p/nKKXt8ZQbmh)]
-   **<big>IsLink</big>** : checks if a file is symbol link or not.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#IsLink)]
    [[play](https://go.dev/play/p/TL-b-Kzvf44)]
-   **<big>IsDir</big>** : checks if the path is directory or not.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#IsDir)]
    [[play](https://go.dev/play/p/WkVwEKqtOWk)]
-   **<big>ListFileNames</big>** : return all file names in the path.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#ListFileNames)]
    [[play](https://go.dev/play/p/Tjd7Y07rejl)]
-   **<big>RemoveFile</big>** : remove file, param should be file path.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#RemoveFile)]
    [[play](https://go.dev/play/p/P2y0XW8a1SH)]
-   **<big>ReadFileToString</big>** : return string of file content.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#ReadFileToString)]
    [[play](https://go.dev/play/p/cmfwp_5SQTp)]
-   **<big>ReadFileByLine</big>** : read file line by line, return string slice of file content.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#ReadFileByLine)]
    [[play](https://go.dev/play/p/svJP_7ZrBrD)]
-   **<big>Zip</big>** : create zip file.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#Zip)]
    [[play](https://go.dev/play/p/j-3sWBp8ik_P)]
-   **<big>UnZip</big>** : unzip the zip file and save it to dest path.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/fileutil.md#UnZip)]
    [[play](https://go.dev/play/p/g0w34kS7B8m)]

### 9. Formatter contains some functions for data formatting.

```go
import "github.com/duke-git/lancet/v2/formatter"
```

#### Function list:

-   **<big>Comma</big>** : add comma to a number value by every 3 numbers from right, ahead by symbol char.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/formatter.md#Comma)]
    [[play](https://go.dev/play/p/eRD5k2vzUVX)]

### 10. Function package can control the flow of function execution and support part of functional programming

```go
import "github.com/duke-git/lancet/v2/function"
```

#### Function list:

-   [After](https://github.com/duke-git/lancet/blob/main/docs/function.md#After)
-   [Before](https://github.com/duke-git/lancet/blob/main/docs/function.md#Before)
-   [Curry](https://github.com/duke-git/lancet/blob/main/docs/function.md#Curry)
-   [Compose](https://github.com/duke-git/lancet/blob/main/docs/function.md#Compose)
-   [Debounced](https://github.com/duke-git/lancet/blob/main/docs/function.md#Debounced)
-   [Delay](https://github.com/duke-git/lancet/blob/main/docs/function.md#Delay)
-   [Pipeline](https://github.com/duke-git/lancet/blob/main/docs/function.md#Pipeline)
-   [Watcher](https://github.com/duke-git/lancet/blob/main/docs/function.md#Watcher)

### 11. Maputil package includes some functions to manipulate map.

```go
import "github.com/duke-git/lancet/v2/maputil"
```

#### Function list:

-   **<big>ForEach</big>** : executes iteratee funcation for every key and value pair in map.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#ForEach)]
    [[play](https://go.dev/play/p/OaThj6iNVXK)]
-   **<big>Filter</big>** : iterates over map, return a new map contains all key and value pairs pass the predicate function.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#Filter)]
    [[play](https://go.dev/play/p/fSvF3wxuNG7)]
-   **<big>Intersect</big>** : iterates over maps, return a new map of key and value pairs in all given maps.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#Intersect)]
    [[play](https://go.dev/play/p/Zld0oj3sjcC)]
-   **<big>Keys</big>** : returns a slice of the map's keys.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#Keys)]
    [[play](https://go.dev/play/p/xNB5bTb97Wd)]
-   **<big>Merge</big>** : merge maps, next key will overwrite previous key.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#Merge)]
    [[play](https://go.dev/play/p/H95LENF1uB-)]
-   **<big>Minus</big>** : creates a map of whose key in mapA but not in mapB.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#Minus)]
    [[play](https://go.dev/play/p/3u5U9K7YZ9m)]
-   **<big>Values</big>** : returns a slice of the map's values.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#Values)]
    [[play](https://go.dev/play/p/CBKdUc5FTW6)]
-   **<big>IsDisjoint</big>** : check two map are disjoint if they have no keys in common.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/maputil.md#IsDisjoint)]
    [[play](https://go.dev/play/p/N9qgYg_Ho6f)]

### 12. Mathutil package implements some functions for math calculation.

```go
import "github.com/duke-git/lancet/v2/mathutil"
```

#### Function list:

-   **<big>Average</big>** :return average value of numbers.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Average)]
    [[play](https://go.dev/play/p/Vv7LBwER-pz)]
-   **<big>Exponent</big>** : calculate x^n for int64.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Exponent)]
    [[play](https://go.dev/play/p/uF3HGNPk8wr)]
-   **<big>Fibonacci</big>** :calculate fibonacci number before n for int.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Fibonacci)]
    [[play](https://go.dev/play/p/IscseUNMuUc)]
-   **<big>Factorial</big>** : calculate x! for uint.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Factorial)]
    [[play](https://go.dev/play/p/tt6LdOK67Nx)]
-   **<big>Max</big>** : return maximum value of numbers.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Max)]
    [[play](https://go.dev/play/p/cN8DHI0rTkH)]
-   **<big>MaxBy</big>** : return the maximum value of a slice using the given comparator function.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#MaxBy)]
    [[play](https://go.dev/play/p/pbe2MT-7DV2)]
-   **<big>Min</big>** : return minimum value of numbers.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Min)]
    [[play](https://go.dev/play/p/21BER_mlGUj)]
-   **<big>MinBy</big>** : return the minimum value of a slice using the given comparator function.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#MinBy)]
    [[play](https://go.dev/play/p/N9qgYg_Ho6f)]
-   **<big>Percent</big>** : calculate the percentage of value to total.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#Percent)]
-   **<big>RoundToFloat</big>** : round up to n decimal places for float64.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#RoundToFloat)]
    [[play](https://go.dev/play/p/ghyb528JRJL)]
-   **<big>RoundToString</big>** : round up to n decimal places for float64, return string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#RoundToString)]
    [[play](https://go.dev/play/p/kZwpBRAcllO)]
-   **<big>TruncRound</big>** : round off n decimal places for int64.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/mathutil.md#TruncRound)]
    [[play](https://go.dev/play/p/aumarSHIGzP)]

### 13. Netutil package contains functions to get net information and send http request.

```go
import "github.com/duke-git/lancet/v2/netutil"
```

#### Function list:

-   [ConvertMapToQueryString](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#ConvertMapToQueryString)
-   [EncodeUrl](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#EncodeUrl)
-   [GetInternalIp](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#GetInternalIp)
-   [GetIps](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#GetIps)
-   [GetMacAddrs](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#GetMacAddrs)
-   [GetPublicIpInfo](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#GetPublicIpInfo)
-   [GetRequestPublicIp](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#GetRequestPublicIp)
-   [IsPublicIP](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#IsPublicIP)
-   [IsInternalIP](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#IsInternalIP)
-   [HttpRequest](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpRequest)
-   [HttpClient](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpClient)
-   [SendRequest](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#SendRequest)
-   [DecodeResponse](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#DecodeResponse)
-   [StructToUrlValues](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#StructToUrlValues)
-   [HttpGet<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpGet)
-   [HttpDelete<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpDelete)
-   [HttpPost<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpPost)
-   [HttpPut<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpPut)
-   [HttpPatch<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#HttpPatch)
-   [ParseHttpResponse](https://github.com/duke-git/lancet/blob/main/docs/netutil.md#ParseHttpResponse)

### 14. Random package implements some basic functions to generate random int and string.

```go
import "github.com/duke-git/lancet/v2/random"
```

#### Function list:

-   [RandBytes](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandBytes)
-   [RandInt](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandInt)
-   [RandString](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandString)
-   [RandUpper](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandUpper)
-   [RandLower](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandLower)
-   [RandNumeral](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandNumeral)
-   [RandNumeralOrLetter](https://github.com/duke-git/lancet/blob/main/docs/random.md#RandNumeralOrLetter)
-   [UUIdV4](https://github.com/duke-git/lancet/blob/main/docs/random.md#UUIdV4)

### 15. Retry package is for executing a function repeatedly until it was successful or canceled by the context.

```go
import "github.com/duke-git/lancet/v2/retry"
```

#### Function list:

-   [Context](https://github.com/duke-git/lancet/blob/main/docs/retry.md#Context)
-   [Retry](https://github.com/duke-git/lancet/blob/main/docs/retry.md#Retry)
-   [RetryFunc](https://github.com/duke-git/lancet/blob/main/docs/retry.md#RetryFunc)
-   [RetryDuration](https://github.com/duke-git/lancet/blob/main/docs/retry.md#RetryDuration)
-   [RetryTimes](https://github.com/duke-git/lancet/blob/main/docs/retry.md#RetryTimes)

### 16. Slice contains some functions to manipulate slice.

```go
import "github.com/duke-git/lancet/v2/slice"
```

#### Function list:

-   [AppendIfAbsent](https://github.com/duke-git/lancet/blob/main/docs/slice.md#AppendIfAbsent)
-   [Contain](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Contain)
-   [ContainSubSlice](https://github.com/duke-git/lancet/blob/main/docs/slice.md#ContainSubSlice)
-   [Chunk](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Chunk)
-   [Compact](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Compact)
-   [Concat](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Concat)
-   [Count](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Count)
-   [CountBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#CountBy)
-   [Difference](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Difference)
-   [DifferenceBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#DifferenceBy)
-   [DifferenceWith](https://github.com/duke-git/lancet/blob/main/docs/slice.md#DifferenceWith)
-   [DeleteAt](https://github.com/duke-git/lancet/blob/main/docs/slice.md#DeleteAt)
-   [Drop](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Drop)
-   [Equal](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Equal)
-   [EqualWith](https://github.com/duke-git/lancet/blob/main/docs/slice.md#EqualWith)
-   [Every](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Every)
-   [Filter](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Filter)
-   [Find](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Find)
-   [FindLast](https://github.com/duke-git/lancet/blob/main/docs/slice.md#FindLast)
-   [Flatten](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Flatten)
-   [FlattenDeep](https://github.com/duke-git/lancet/blob/main/docs/slice.md#FlattenDeep)
-   [ForEach](https://github.com/duke-git/lancet/blob/main/docs/slice.md#ForEach)
-   [GroupBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#GroupBy)
-   [GroupWith](https://github.com/duke-git/lancet/blob/main/docs/slice.md#GroupWith)
-   [IntSlice<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/slice.md#IntSlice)
-   [InterfaceSlice<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/slice.md#InterfaceSlice)
-   [Intersection](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Intersection)
-   [InsertAt](https://github.com/duke-git/lancet/blob/main/docs/slice.md#InsertAt)
-   [IndexOf](https://github.com/duke-git/lancet/blob/main/docs/slice.md#IndexOf)
-   [LastIndexOf](https://github.com/duke-git/lancet/blob/main/docs/slice.md#LastIndexOf)
-   [Map](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Map)
-   [Merge](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Merge)
-   [Reverse](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Reverse)
-   [Reduce](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Reduce)
-   [Replace](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Replace)
-   [ReplaceAll](https://github.com/duke-git/lancet/blob/main/docs/slice.md#ReplaceAll)
-   [Repeat](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Repeat)
-   [Shuffle](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Shuffle)
-   [Sort](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Sort)
-   [SortBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#SortBy)
-   [SortByField<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/slice.md#SortByField)
-   [Some](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Some)
-   [StringSlice<sup>deprecated</sup>](https://github.com/duke-git/lancet/blob/main/docs/slice.md#StringSlice)
-   [SymmetricDifference](https://github.com/duke-git/lancet/blob/main/docs/slice.md#SymmetricDifference)
-   [ToSlice](https://github.com/duke-git/lancet/blob/main/docs/slice.md#ToSlice)
-   [ToSlicePointer](https://github.com/duke-git/lancet/blob/main/docs/slice.md#ToSlicePointer)
-   [Unique](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Unique)
-   [UniqueBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#UniqueBy)
-   [Union](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Union)
-   [UnionBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#UnionBy)
-   [UpdateAt](https://github.com/duke-git/lancet/blob/main/docs/slice.md#UpdateAt)
-   [Without](https://github.com/duke-git/lancet/blob/main/docs/slice.md#Without)
-   [KeyBy](https://github.com/duke-git/lancet/blob/main/docs/slice.md#KeyBy)

### 17. Strutil package contains some functions to manipulate string.

```go
import "github.com/duke-git/lancet/v2/strutil"
```

#### Function list:

-   **<big>After</big>** : returns the substring after the first occurrence of a specified string in the source string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#After)]
    [[play](https://go.dev/play/p/RbCOQqCDA7m)]
-   **<big>AfterLast</big>** : returns the substring after the last occurrence of a specified string in the source string. [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#AfterLast)]
    [[play](https://go.dev/play/p/1TegARrb8Yn)]
-   **<big>Before</big>** : returns the substring before the first occurrence of a specified string in the source string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#Before)]
    [[play](https://go.dev/play/p/JAWTZDS4F5w)]
-   **<big>BeforeLast</big>** : returns the substring before the last occurrence of a specified string in the source string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#BeforeLast)]
    [[play](https://go.dev/play/p/pJfXXAoG_Te)]
-   **<big>CamelCase</big>** : coverts source string to its camelCase string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#CamelCase)]
    [[play](https://go.dev/play/p/9eXP3tn2tUy)]
-   **<big>Capitalize</big>** : converts the first character of source string to upper case and the remaining to lower case.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#Capitalize)]
    [[play](https://go.dev/play/p/2OAjgbmAqHZ)]
-   **<big>IsString</big>** : checks if the parameter value data type is string or not.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#IsString)]
    [[play](https://go.dev/play/p/IOgq7oF9ERm)]
-   **<big>KebabCase</big>** : coverts string to kebab-case string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#KebabCase)]
    [[play](https://go.dev/play/p/dcZM9Oahw-Y)]
-   **<big>UpperKebabCase</big>** : coverts string to upper KEBAB-CASE string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#UpperKebabCase)]
    [[play](https://go.dev/play/p/zDyKNneyQXk)]
-   **<big>LowerFirst</big>** : converts the first character of string to lower case.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#LowerFirst)]
    [[play](https://go.dev/play/p/CbzAyZmtJwL)]
-   **<big>UpperFirst</big>** : converts the first character of string to upper case.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#UpperFirst)]
    [[play](https://go.dev/play/p/sBbBxRbs8MM)]
-   **<big>PadEnd</big>** : pads string with given characters on the right side if it's shorter than limit size. Padding characters are truncated if they exceed size.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#PadEnd)]
    [[play](https://go.dev/play/p/9xP8rN0vz--)]
-   **<big>PadStart</big>** : pads string with given characters on the left side if it's shorter than limit size. Padding characters are truncated if they exceed size.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#PadStart)]
    [[play](https://go.dev/play/p/xpTfzArDfvT)]
-   **<big>Reverse</big>** : returns string whose char order is reversed to the given string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#Reverse)]
    [[play](https://go.dev/play/p/adfwalJiecD)]
-   **<big>SnakeCase</big>** : coverts string to snake_case string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#SnakeCase)]
    [[play](https://go.dev/play/p/tgzQG11qBuN)]
-   **<big>UpperSnakeCase</big>** : coverts string to upper SNAKE_CASE string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#UpperSnakeCase)]
    [[play](https://go.dev/play/p/4COPHpnLx38)]
-   **<big>SplitEx</big>** : split a given string which can control the result slice contains empty string or not.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#SplitEx)]
    [[play](https://go.dev/play/p/Us-ySSbWh-3)]
-   **<big>Substring</big>** : returns a substring of the specified length starting at the specified offset position.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#Substring)]
-   **<big>Wrap</big>** : wrap a string with given string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#Wrap)]
    [[play](https://go.dev/play/p/KoZOlZDDt9y)]
-   **<big>Unwrap</big>** : unwrap a given string from anther string. will change source string.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/strutil.md#Unwrap)]
    [[play](https://go.dev/play/p/Ec2q4BzCpG-)]

### 19. System package contain some functions about os, runtime, shell command.

```go
import "github.com/duke-git/lancet/v2/system"
```

#### Function list:

-   **<big>IsWindows</big>** : check if current os is windows.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#IsWindows)]
    [[play](https://go.dev/play/p/XzJULbzmf9m)]
-   **<big>IsLinux</big>** : check if current os is linux.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#IsLinux)]
    [[play](https://go.dev/play/p/zIflQgZNuxD)]
-   **<big>IsMac</big>** : check if current os is macos.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#IsMac)]
    [[play](https://go.dev/play/p/Mg4Hjtyq7Zc)]
-   **<big>GetOsEnv</big>** : get the value of the environment variable named by the key.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#GetOsEnv)]
    [[play](https://go.dev/play/p/D88OYVCyjO-)]
-   **<big>SetOsEnv</big>** : set the value of the environment variable named by the key.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#SetOsEnv)]
    [[play](https://go.dev/play/p/D88OYVCyjO-)]
-   **<big>RemoveOsEnv</big>** : remove a single environment variable.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#RemoveOsEnv)]
    [[play](https://go.dev/play/p/fqyq4b3xUFQ)]
-   **<big>CompareOsEnv</big>** : get env named by the key and compare it with passed env.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#CompareOsEnv)]
    [[play](https://go.dev/play/p/BciHrKYOHbp)]
-   **<big>ExecCommand</big>** : execute command, return the stdout and stderr string of command, and error if error occurs.
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#ExecCommand)]
    [[play](https://go.dev/play/p/n-2fLyZef-4)]
-   **<big>GetOsBits</big>** : return current os bits (32 or 64).
    [[doc](https://github.com/duke-git/lancet/blob/main/docs/system.md#GetOsBits)]
    [[play](https://go.dev/play/p/ml-_XH3gJbW)]

### 19. Validator package contains some functions for data validation.

```go
import "github.com/duke-git/lancet/v2/validator"
```

#### Function list:

-   [ContainChinese](https://github.com/duke-git/lancet/blob/main/docs/validator.md#ContainChinese)
-   [ContainLetter](https://github.com/duke-git/lancet/blob/main/docs/validator.md#ContainLetter)
-   [ContainLower](https://github.com/duke-git/lancet/blob/main/docs/validator.md#ContainLower)
-   [ContainUpper](https://github.com/duke-git/lancet/blob/main/docs/validator.md#ContainUpper)
-   [IsAlpha](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsAlpha)
-   [IsAllUpper](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsAllUpper)
-   [IsAllLower](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsAllLower)
-   [IsBase64](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsBase64)
-   [IsChineseMobile](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsChineseMobile)
-   [IsChineseIdNum](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsChineseIdNum)
-   [IsChinesePhone](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsChinesePhone)
-   [IsCreditCard](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsCreditCard)
-   [IsDns](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsDns)
-   [IsEmail](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsEmail)
-   [IsEmptyString](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsEmptyString)
-   [IsFloatStr](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsFloatStr)
-   [IsNumberStr](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsNumberStr)
-   [IsJSON](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsJSON)
-   [IsRegexMatch](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsRegexMatch)
-   [IsIntStr](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsIntStr)
-   [IsIp](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsIp)
-   [IsIpV4](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsIpV4)
-   [IsIpV6](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsIpV6)
-   [IsStrongPassword](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsStrongPassword)
-   [IsUrl](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsUrl)
-   [IsWeakPassword](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsWeakPassword)
-   [IsZeroValue](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsZeroValue)
-   [IsGBK](https://github.com/duke-git/lancet/blob/main/docs/validator.md#IsGBK)

### 20. xerror package implements helpers for errors.

```go
import "github.com/duke-git/lancet/v2/xerror"
```

#### Function list:

-   [Unwrap](https://github.com/duke-git/lancet/blob/main/docs/xerror.md#Unwrap)

## How to Contribute

I really appreciate any code commits which make lancet lib powerful. Please follow the rules below to create your pull request.

1. Fork the repository.
2. Create your feature branch.
3. Commit your changes.
4. Push to the branch
5. Create new pull request.
