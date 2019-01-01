# test1

## test2
	asd
### 1789
	1. 간결하다.

> asdas
>> asdasd

[Google][googlelink]
* 빨강
	* 녹색
+ 빨강
  + 녹색

- 빨강
  - 녹색
--------------------
[googlelink]: https://google.com "Go google"

*single asterisks*<p/>
_single underscores_<p/>
**double asterisks**<p/>
__double underscores__<p/>
<p>This is a <u>parragraph</u>.</p>
~~cancelline~~ <br/>

#### test1
* ra1
* ra2
#### test2
#### test3
	code line test
	asda

	
First Header | Second Header
------------ | -------------
Content cell 1 | Content cell 2
Content column 1 | Content column 2
	First Header | Second Header
	------------ | -------------
	Content cell 1 | Content cell 2
	Content column 1 | Content column 2
asdasd
asdasd
```code```

```cpp
int main() {
  int y = SOME_MACRO_REFERENCE;
  int x = 5 + 6;
  cout << "Hello World! " << x << std::endl();
}
```

Testing <sub>subscript</sub> and <sup>superscript</sup>

Testing <sub>subscript <sub>subscript level 2</sub></sub>

Testing <sup>superscript <sup>superscript level 2</sup></sup>


A<sub>i,j</sub>
A<sup>i,j</sup>


<ins>just in github?</ins>
---------
The merge of the array of 3channel mat gives the wrong result on a particular input.
--------------


When an array of mat entering as input type If each Mat is not a single channel, but array of three or four Mat's of the three channels is input, the '''ipp_merge()''' branch will result in an incorrect merge.
```ipp_merge ()``` seems to have been implemented assuming that the ```Mat``` channels are all 1 channel.
Therefore, we must move the ```ipp_merge()``` call below the ```if (! Allch1)``` branch to work properly.

This function is implemented assuming that all mat channels are all 1 channel.

 '''ipp_merge()''' is probably implemented assuming that all the ```Mat``` channels are all 1 channel.
 

Therefore, we must move the ipp_merge function call below the "if (! Allch1)" branch to work properly.


### System information (version)
* OpenCV => master
* Operating System / Platform => Windows 10 64-Bit , CUDA 8.0
* Compiler => Visual Studio 2015

### Detailed description
If I call cv::cuda::Stream::Null() in my code, it seems it calls ```cudaMalloc()``` without freeing the allocated memory, resulting in a memory leak error when tested with the command line memory checker ```cuda-memcheck --leak-check full```.
### Steps to reproduce
```cuda
__global__ void hello()
{
	printf("%u: hello\n", threadIdx.x);
}
int main()
{
	hello<<<1, 16, 0, cv::cuda::StreamAccessor::getStream(cv::cuda::Stream::Null())>>>();
	CheckCudaError(cudaDeviceSynchronize());
	CheckCudaError(cudaDeviceReset());
}
```
