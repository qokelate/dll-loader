# DLL注入器

## 1.Usage:

```
# 常规注入
-ip|--inject-dll-to-pid <dll> <pid>
-in|--inject-dll-to-process <dll> <process-name>
-ir|--create-process-with-dll <dll> <command> [args...]
-it|--load-dll <dll> [--keep|dll] [--keep|dll] [....]

# 内存方式注入(注入后不依赖本地DLL文件)
-mp|--inject-memdll-to-pid <dll> <pid>
-mn|--inject-memdll-to-process <dll> <process-name>
-mr|--create-process-with-memdll <dll> <command> [args...]
-mt|--load-memdll <dll> [--keep|dll] [--keep|dll] [....]

BTW:
  libconsole.dll show console if inject success.
```

## 2.Example

```
# 常规方式, 执行命令行并注入DLL
dll-loader.exe -ir libconsole.dll winver.exe

# 常规方式, 注入DLL到指定PID
dll-loader.exe -ip libconsole.dll 1234


# 内存方式,加载DLL到内存,然后注入到进程,注入后不依赖本地DLL
dll-loader.exe -mr libconsole.dll winver.exe

# 内存方式,加载DLL到内存,然后注入到指定PID,注入后不依赖本地DLL
dll-loader.exe -mp libconsole.dll 1234
```

## 3.特别说明

### 必须同架构注入,即X86注入32位进程, X64注入64位进程