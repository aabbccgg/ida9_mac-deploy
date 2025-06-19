* 构建版本2024-0925 
* 原生支持linux mac win
```
magnet:?xt=urn:btih:920c1a578e815e9d0e4b843179306cdcb5e8e00d&dn=idapro90rc1
```
* 9.1版本
```
magnet:?xt=urn:btih:f24cfadb8a66b343bf1ff4f0c1386a5f6991c818&dn=ida91
```

mac使用方法：
```
请确认你的ida pro version
IDA_PATH=/Applications/IDA\ Professional\ 9.1.app/

cd kg_patch
cp -f ${IDA_PATH}Contents/MacOS/libida.dylib ./
cp -f ${IDA_PATH}Contents/MacOS/libida32.dylib ./

9.0:
python keygen2.py
9.1:
python keygen3.py

mv -f libida.dylib.patched ${IDA_PATH}Contents/MacOS/libida.dylib
mv -f libida32.dylib.patched ${IDA_PATH}Contents/MacOS/libida32.dylib
sudo codesign -f -s - ${IDA_PATH}Contents/MacOS/libida.dylib
sudo codesign -f -s - ${IDA_PATH}Contents/MacOS/libida32.dylib
//sudo xattr -cr ${IDA_PATH}
```

在9.0中开启idapython，可能会用到（9.1已经可以自动识别了）
```
cd /Applications/IDA\ Professional\ 9.0.app/Contents/MacOS
./idapyswitch

# 选择你的venv使用的python
```

设置idapython venv
```
# 修改idapythonrc.py文件中mypath为你venv的路径
cp idapythonrc.py /User/name/.idapro
```

完整ida feeds支持#目前会导致PyQt5无法被引用，从而加载失败
```
cd /Applications/IDA\ Professional\ 9.0.app/Contents/MacOS/plugins/ida_feeds
pip install -r requirements.txt
`mkdir $HOME/.idapro/plugins`
`ln -s "$(pwd)" $HOME/.idapro/plugins/`
```
