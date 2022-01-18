# 8086
一些8086的杂物

## 8086,5x,10x,50x.mirrored.png
使用金相显微镜拍摄的Intel D8086（串号L6180495）的照片，目镜5x，物镜10x，总放大倍数50x，图片被镜像

![未镜像缩略图]https://i0.hdslb.com/bfs/album/fa5ad472556da38004f5a26fb4081d6767148fe8.png

## ch375.bin
CH375的BIOS，默认地址260-261，默认驱动器号0x80，默认读取4次61端口用于延时，修改后需要修改最后一字节使校验和为0
```
    CPU     8086

            ORG     0
SECTION     0
            DW  0AA55H               ; MAGIC NUMBER
SIZE        EQU 4
            DB  2*SIZE               ; 4KB
            JMP CH375MAIN

ADDR_PACK   DB  10H
            DB  0
            DW  1
            DD  0
            DQ  0



CH375ADDR   DW  260H
MYDRVLETTER DB  80H
DELAY_TIME  DB  4
;----- 后续代码省略
```
