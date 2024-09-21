{
FileLocator root.   "File system's root (/)"
FileLocator C.      "Windows C:\"
home := FileLocator home.

home pathString
> '/home/cassou/'

home children
> an Array({home}/.bashrc {home}/Music ...)
> an Array({home}/Music/Anouar_Brahem ...)
> '/home/cassou/'
music := FileLocator home / 'Music'.
(music / 'Pink_Floyd') isDirectory.
> false

(music / 'Pink_Floyd') ensureCreateDirectory.
(music / 'Pink_Floyd') isDirectory.
> true

(music / 'Pink_Floyd') delete.
(music / 'Pink_Floyd') isDirectory
> false
   select: [ :each | each basename endsWith: 'ogg' ]
pharo := 'pharo.image' asFileReference.

pharo isFile.
> true

pharo basename
> 'pharo.image'

pharo extension
> 'image'

pharo size
> 23744868

pharo parent pathString
> '/home/cassou/Pharo/images/pharo'
hello := 'hello.txt' asFileReference.
hello exists
> false

stream := hello writeStream.
stream nextPutAll: 'Hello World'.
stream close.
hello := 'hello.txt' asFileReference.
hello exists
> true

stream := hello readStream.
stream next.
> $H

stream upToEnd.
> 'ello World'

stream close
hello := 'hello.txt' asFileReference.
   stream nextPutAll: 'Hello World'].
> 'Hello World'