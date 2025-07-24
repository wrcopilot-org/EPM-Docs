# EPM (EaseUS Partition Master) 错误码信息手册

## 错误信息结构设计

```
错误信息结构:
{
  "errorCode": "错误码(16进制)",
  "errorName": "错误定义名称",
  "category": "错误分类",
  "errorMessage": "错误描述信息",
  "baseCode": "基础错误码",
  "module": "所属模块",
  "severity": "严重程度",
  "possibleCauses": ["可能原因"],
  "suggestedActions": ["建议操作"]
}
```

## 错误码分类体系

### 1. 基础错误码 (0x0000 - 0x3FF)
基础系统错误，包括成功、失败、版本不匹配等通用错误。

### 2. 网络通信错误码 (0x0200 系列)
网络通信、传输、命令包相关错误。

### 3. FAT文件系统错误码 (0xF000 系列)
FAT文件系统操作相关错误。

### 4. NTFS文件系统错误码 (0xF0000000 系列) 
NTFS文件系统操作相关错误。

### 5. FAT拷贝错误码 (0x1F000 系列)
FAT文件系统拷贝操作相关错误。

### 6. FTP错误码 (UTE系列)
FTP客户端通信相关错误。

### 7. USB磁盘格式化错误码 (0x1200 系列)
USB磁盘格式化操作相关错误。

### 8. FAT转NTFS错误码 (0xFE000 系列)
FAT文件系统转换为NTFS文件系统的错误。

### 9. TBC云错误码 (TBCE系列)
Todo Backup Cloud相关错误。

### 10. ESE数据库错误码 (HRESULT系列)
Exchange Server数据库相关错误。

### 11. 通用还原错误码 (0x02B0 系列)
Universal Restore通用还原相关错误。

### 12. 设备管理错误码
设备访问、驱动程序相关错误。

## 详细错误码信息

### 基础错误码 (0x0000 - 0x3FF)

| 错误码 | 错误名称 | 中文描述 | 分类 |
|--------|----------|----------|------|
| 0x0000 | BP_ERR_SUCCESS | 成功 | 成功 |
| 0x0001 | BP_ERR_FALSE | 失败 | 通用错误 |
| 0x0002 | BP_ERR_DLL_VER | DLL版本错误 | 版本错误 |
| 0x0003 | BP_ERR_VERSION | 版本不匹配 | 版本错误 |
| 0x0004 | BP_ERR_NOT_FOUND_FILE | 文件未找到 | 文件错误 |
| 0x0005 | BP_ERR_NOT_INIT | 未初始化 | 初始化错误 |
| 0x0006 | BP_ERR_NOT_SUPPORT | 不支持的操作 | 功能错误 |
| 0x0007 | BP_ERR_BUSY | 系统忙 | 状态错误 |
| 0x0008 | BP_ERR_NOT_ENOUGH_MEMORY | 内存不足 | 资源错误 |
| 0x0009 | BP_ERR_INVALID_PARAM | 无效参数 | 参数错误 |
| 0x000A | BP_ERR_NULL_POINTER | 空指针 | 参数错误 |
| 0x000B | BP_ERR_NO_DISKSPACE | 磁盘空间不足 | 资源错误 |
| 0x000C | BP_ERR_INVALID_DATA | 无效数据 | 数据错误 |
| 0x000D | BP_ERR_TOO_LONG_PATH | 路径过长 | 路径错误 |
| 0x000E | BP_ERR_OUT_OF_BUFFER | 缓冲区溢出 | 缓冲区错误 |
| 0x000F | BP_ERR_NETWORK | 网络错误 | 网络错误 |
| 0x0010 | BP_ERR_NETWORK_CONNECT | 网络连接错误 | 网络错误 |
| 0x0011 | BP_ERR_TIMEOUT | 超时 | 超时错误 |
| 0x0012 | BP_ERR_SEND_DATA | 发送数据失败 | 网络错误 |
| 0x0013 | BP_ERR_NO_ADMINS | 没有管理员权限 | 权限错误 |
| 0x001A | BP_ERR_USER_CANCEL | 用户取消 | 用户操作 |

### 网络通信错误码 (0x0200 系列)

| 错误码 | 错误名称 | 中文描述 | 模块 |
|--------|----------|----------|------|
| 0x0201 | BP_ERR_NETMANAGER_NULL | 网络通信对象指针为空 | 网络通信 |
| 0x0202 | BP_ERR_GET_ADDRESS | 获取模块地址失败 | 网络通信 |
| 0x0203 | BP_ERR_CREATENETMANAGER | 创建网络通信对象失败 | 网络通信 |
| 0x0204 | BP_ERR_INITNETSERVICE | 初始化网络服务失败 | 网络通信 |
| 0x0206 | BP_ERR_CANCELED_COMMAND | 已经取消命令 | 命令处理 |
| 0x0207 | BP_ERR_WAIT_TIMEOUT | 异步命令超时 | 超时错误 |
| 0x0208 | BP_ERR_CREATE_COMMUNICATOR | 创建底层通讯对象失败 | 通讯 |
| 0x0209 | BP_ERR_WAIT_FAILED | 同步命令等待超时或失败 | 同步错误 |
| 0x020A | BP_ERR_INVALID_TRANSMIT_TYPE | 非法的Transmit类型 | 传输错误 |
| 0x020B | BP_ERR_PACKAGE_PROPERY | 非法的包属性 | 包处理 |
| 0x020C | BP_ERR_START_COMPUTER_DECTECT | 启动广播监控失败 | 设备检测 |
| 0x020D | BP_ERR_CREATE_SHIFT | 创建命令传输对象Shift失败 | 传输错误 |
| 0x020E | BP_ERR_INVALID_SHIFT | 非法命令传输对象Shift | 传输错误 |

### FAT文件系统错误码 (0xF000 系列)

| 错误码 | 错误名称 | 中文描述 | 操作类型 |
|--------|----------|----------|----------|
| 0xF001 | FAT_DEVICE_POINTER_INVALID | 设备指针无效 | 设备操作 |
| 0xF002 | FAT_GET_FILE_SYSTEM_INFO_ERROR | 获取文件系统信息错误 | 信息获取 |
| 0xF003 | FAT_CHECK_FILE_SYSTEM_ERROR | 检查文件系统错误 | 文件系统检查 |
| 0xF004 | FAT_RESIZE_MOVE_PROCESS_ERROR | Resize/Move过程中出现错误 | 分区操作 |
| 0xF005 | FAT_USER_CANCLE_ERROR | 用户中止操作 | 用户操作 |
| 0xF006 | FAT_FORMAT_PROCESS_ERROR | Format过程出现错误 | 格式化 |
| 0xF007 | FAT_NO_ENOUGH_MEMORY_ERROR | 内存不够 | 内存错误 |
| 0xF008 | FAT_NO_ENOUGH_FREE_SPACE_ERROR | 在Resize/move的方向没有足够的可用空间 | 空间不足 |
| 0xF01B | FAT_GET_USER_SPACE_ERROR | 获取已使用空间错误 | 空间计算 |
| 0xF01C | FAT_MOVE_PARTITION_ERROR | 移动分区错误 | 分区移动 |
| 0xF020 | FAT_SET_PARTITION_LABLE_ERROR | 设置卷标错误 | 卷标设置 |
| 0xF021 | FAT_GET_PARTITION_LABLE_ERROR | 获取卷标错误 | 卷标获取 |
| 0xF025 | FAT_NO_FREE_FDT_ERROR | 设置卷标时FAT16/12中没有可用FDT项重复此错误 | FDT错误 |
| 0xF026 | FAT_PARTITION_NO_LABLE_ERROR | 分区没有卷标 | 卷标错误 |
| 0xF029 | FAT_OPEN_DEVICE_ERROR | 打开设备失败 | 设备操作 |
| 0xF02A | FAT_CLOSET_DEVICE_ERROR | 关闭设备失败 | 设备操作 |
| 0xF02B | FAT_LIB_INIT_ERROR | Fat库初始化失败 | 初始化 |
| 0xF02C | FAT_GET_CLUSTER_SIZE_ERROR | 获取簇大小错误 | 簇操作 |
| 0xF02D | FAT_GET_RESIZE_MAX_MIN_SIZE_ERROR | 获取Resize的最大最小限制错误 | 大小计算 |
| 0xF02E | FAT_TEST_RESIZE_SPACE_ERROR | 测试Resize空间是否足够错误 | 空间测试 |

### FAT文件系统扩展错误码

| 错误码 | 错误名称 | 中文描述 | 详细说明 |
|--------|----------|----------|----------|
| 0xF162 | FAT_CHECK_EXT_ERROR_FAT1_FAT2 | FAT1与FAT2不匹配 | FAT表检查 |
| 0xF163 | FAT_CHECK_EXT_ERROR_FAT_BUF | FAT缓冲区错误 | 缓冲区错误 |
| 0xF164 | FAT_CHECK_EXT_ERROR_FAT_REBUILD | FAT重建错误 | FAT重建 |
| 0xF165 | FAT_CHECK_EXT_ERROR_CHECK_PARM | 检查参数错误 | 参数检查 |
| 0xF166 | FAT_CHECK_EXT_ERROR_CHECK_PARM_IN | 输入参数检查错误 | 输入参数 |
| 0xF167 | FAT_CHECK_EXT_ERROR_ROOT_BUF | 根目录缓冲区错误 | 根目录错误 |
| 0xF168 | FAT_CHECK_EXT_ERROR_ROOT_GET | 获取根目录错误 | 根目录访问 |
| 0xF169 | FAT_CHECK_EXT_ERROR_ROOT_GET32 | 获取FAT32根目录错误 | FAT32根目录 |
| 0xF16A | FAT_CHECK_EXT_ERROR_FAT_FILL | FAT填充错误 | FAT填充 |
| 0xF16B | FAT_CHECK_EXT_ERROR_SYSTEM_TYPE | 系统类型错误 | 系统类型 |
| 0xF16C | FAT_CHECK_EXT_ERROR_DIR_GET | 目录获取错误 | 目录访问 |
| 0xF16D | FAT_CHECK_EXT_ERROR_FAT_FILL_DIR | FAT目录填充错误 | 目录填充 |
| 0xF16E | FAT_CHECK_EXT_ERROR_DIR_ISNOT_DIR | 目录项不是目录 | 目录类型 |
| 0xF16F | FAT_CHECK_EXT_ERROR_CHAIN_GET | 簇链获取错误 | 簇链操作 |
| 0xF170 | FAT_CHECK_EXT_ERROR_FAT_FILL_FILE | FAT文件填充错误 | 文件填充 |
| 0xF171 | FAT_CHECK_EXT_ERROR_DIR_ISNOT_DIR_X | 扩展目录项不是目录 | 扩展目录 |
| 0xF172 | FAT_CHECK_EXT_ERROR_CUR_DIR | 当前目录错误 | 当前目录 |
| 0xF173 | FAT_CHECK_EXT_ERROR_PARENT_DIR | 父目录错误 | 父目录 |

### NTFS文件系统错误码 (0xF0000000 系列)

| 错误码 | 错误名称 | 中文描述 | 操作类型 |
|--------|----------|----------|----------|
| 0xF0000000 | NTFS_ERROR_NOERROR | 无错误 | 成功 |
| 0xF0000001 | NTFS_ERROR_USER_CANCELED | 用户取消 | 用户操作 |
| 0xF0000002 | NTFS_ERROR_WRITE_SECTOR | 写扇区错误 | 磁盘写入 |
| 0xF0000003 | NTFS_ERROR_READ_SECTOR | 读扇区错误 | 磁盘读取 |
| 0xF0000004 | NTFS_ERROR_TOO_MANY_BAD_CLUSTER | 坏簇过多 | 坏簇检测 |
| 0xF0000005 | NTFS_ERROR_NOT_ENOUGH_MEMORY | 内存不足 | 内存错误 |
| 0xF0000006 | NTFS_ERROR_TOO_MANY_FRAGMENT | 碎片过多 | 碎片整理 |
| 0xF0000007 | NTFS_ERROR_NEED_MORE_UNUSED_FILERECORD | 需要更多未使用的文件记录 | 文件记录 |
| 0xF0000008 | NTFS_ERROR_NEED_MORE_FREE_SPACE | 需要更多可用空间 | 空间不足 |
| 0xF0000009 | NTFS_ERROR_CHECK_FAILED | 检查失败 | 文件系统检查 |
| 0xF000000A | NTFS_ERROR_DONOT_SUPPORT | 不支持 | 功能限制 |
| 0xF000000B | NTFS_ERROR_INVALID_PARAMETER | 无效参数 | 参数错误 |
| 0xF000000C | NTFS_ERROR_CALLBACK_RETURN_UNKNOWN_ERROR | 回调返回未知错误 | 回调错误 |
| 0xF000000D | NTFS_ERROR_OPEN_DISK_FAILED | 打开磁盘失败 | 磁盘访问 |
| 0xFFFFFFFF | NTFS_ERROR_UNKNOWN | 未知错误 | 未知错误 |

### NTFS移动/调整大小错误码

| 错误码 | 错误名称 | 中文描述 | 操作类型 |
|--------|----------|----------|----------|
| 0xF0000160 | NTFS_ERROR_MOVE_LOAD_VOLUMN | 移动时加载卷错误 | 卷移动 |
| 0xF0000161 | NTFS_ERROR_MOVE_INIT_MFT | 移动时初始化MFT错误 | MFT操作 |
| 0xF0000162 | NTFS_ERROR_MOVE_BAD_CLUSTER | 移动时坏簇错误 | 坏簇处理 |
| 0xF0000163 | NTFS_ERROR_MOVE_LOAD_BITMAP | 移动时加载位图错误 | 位图操作 |
| 0xF000016A | NTFS_ERROR_RESIZE_LOAD_VOLUMN | 调整大小时加载卷错误 | 卷调整 |
| 0xF000016B | NTFS_ERROR_RESIZE_INIT_MFT | 调整大小时初始化MFT错误 | MFT操作 |
| 0xF000016C | NTFS_ERROR_RESIZE_BAD_CLUSTER | 调整大小时坏簇错误 | 坏簇处理 |
| 0xF000016D | NTFS_ERROR_RESIZE_LOAD_BITMAP | 调整大小时加载位图错误 | 位图操作 |
| 0xF000016E | NTFS_ERROR_RESIZE_FRAGMENT | 调整大小时碎片错误 | 碎片处理 |

### NTFS拷贝错误码

| 错误码 | 错误名称 | 中文描述 | 操作阶段 |
|--------|----------|----------|----------|
| 0xF00001AE | NTFS_ERROR_COPY_INIT_VOLUMN | 拷贝初始化卷错误 | 初始化 |
| 0xF00001AF | NTFS_ERROR_COPY_LOAD_VOLUMN | 拷贝加载卷错误 | 加载阶段 |
| 0xF00001B0 | NTFS_ERROR_COPY_LOAD_$MFT | 拷贝加载$MFT错误 | MFT加载 |
| 0xF00001B1 | NTFS_ERROR_COPY_LOAD_$BITMAP | 拷贝加载$BITMAP错误 | 位图加载 |
| 0xF00001B2 | NTFS_ERROR_COPY_LOAD_$MFT$BITMAP | 拷贝加载$MFT$BITMAP错误 | MFT位图 |
| 0xF00001B3 | NTFS_ERROR_COPY_INIT_$BITMAP | 拷贝初始化$BITMAP错误 | 位图初始化 |
| 0xF00001B4 | NTFS_ERROR_COPY_INIT_$MFT | 拷贝初始化$MFT错误 | MFT初始化 |
| 0xF00001B5 | NTFS_ERROR_COPY_INIT_$MFT$BITMAP | 拷贝初始化$MFT$BITMAP错误 | MFT位图初始化 |
| 0xF00001B6 | NTFS_ERROR_COPY_VERIFY_VOLUME | 拷贝验证卷错误 | 卷验证 |
| 0xF00001B7 | NTFS_ERROR_COPY_COLLECT_RECORD | 拷贝收集记录错误 | 记录收集 |
| 0xF00001B8 | NTFS_ERROR_COPY_NORMAL_RECORD | 拷贝普通记录错误 | 普通记录 |
| 0xF00001B9 | NTFS_ERROR_COPY_MULTI_RECORD | 拷贝多记录错误 | 多记录 |
| 0xF00001BA | NTFS_ERROR_COPY_SAVE_$MFT$BITMAP | 拷贝保存$MFT$BITMAP错误 | MFT位图保存 |
| 0xF00001BB | NTFS_ERROR_COPY_SAVE_$BITMAP | 拷贝保存$BITMAP错误 | 位图保存 |
| 0xF00001BC | NTFS_ERROR_COPY_SAVE_$LOGFILE | 拷贝保存$LOGFILE错误 | 日志文件 |
| 0xF00001BD | NTFS_ERROR_COPY_SAVE_$BADCLUSTER | 拷贝保存$BADCLUSTER错误 | 坏簇保存 |
| 0xF00001BE | NTFS_ERROR_COPY_SAVE_$MFTMIRR | 拷贝保存$MFTMIRR错误 | MFT镜像 |
| 0xF00001BF | NTFS_ERROR_COPY_SAVE_$BOOT | 拷贝保存$BOOT错误 | 引导保存 |
| 0xF00001C0 | NTFS_ERROR_COPY_WRITE_RECORDS | 拷贝写入记录错误 | 记录写入 |
| 0xF00001C1 | NTFS_ERROR_COPY_WRITE_MULTIRECORDS | 拷贝写入多记录错误 | 多记录写入 |
| 0xF00001C2 | NTFS_ERROR_COPY_UPDATE_$MFT | 拷贝更新$MFT错误 | MFT更新 |
| 0xF00001C3 | NTFS_ERROR_COPY_LOAD_$BADCLUS$BAD | 拷贝加载$BADCLUS$BAD错误 | 坏簇加载 |
| 0xF00001C4 | NTFS_ERROR_COPY_INIT_$BADCLUS$BAD | 拷贝初始化$BADCLUS$BAD错误 | 坏簇初始化 |

### FAT拷贝错误码 (0x1F000 系列)

| 错误码 | 错误名称 | 中文描述 | 操作类型 |
|--------|----------|----------|----------|
| 0x1F001 | FC_CHECK_FILE_SYSTEM_ERROR | 文件系统检查错误 | 文件系统检查 |
| 0x1F002 | FC_CHECK_FAT1_NEQ_FAT2 | FAT1与FAT2不相等 | FAT表验证 |
| 0x1F003 | FC_CHECK_FAT_NEQ_FATX | FAT与FATX不相等 | FAT表验证 |
| 0x1F004 | FC_CHECK_PROCESS_FDT_ERROR | 处理FDT错误 | FDT处理 |
| 0x1F005 | FC_CHECK_GET_CLUSTER_CHAIN_ERROR | 获取簇链错误 | 簇链操作 |
| 0x1F006 | FC_COPY_INIT_FAILED | 拷贝初始化失败 | 初始化 |
| 0x1F007 | FC_COPY_UNKNOWN_FILESYSTEM | 未知文件系统 | 文件系统识别 |
| 0x1F008 | FC_COPY_VERIFY_SIZE_FAILED | 验证大小失败 | 大小验证 |
| 0x1F009 | FC_COPY_PROCESS_FAT_FAILED | 处理FAT失败 | FAT处理 |
| 0x1F00A | FC_COPY_FAT2FATX_FAILED | FAT到FATX拷贝失败 | FAT转换 |
| 0x1F00B | FC_COPY_ERROR | 拷贝错误 | 拷贝操作 |
| 0x1F00C | FC_UPDATE_FS_FAILED | 更新文件系统失败 | 文件系统更新 |
| 0x1F00D | FC_FATX_PROCESS_FAILED | FATX处理失败 | FATX处理 |
| 0x1F00E | FC_NO_ENOUGH_FREE_SPACE_ERROR | 没有足够的可用空间 | 空间不足 |
| 0x1F00F | FC_UPDATE_CLUSTER_NO_FAILED | 更新簇号失败 | 簇号更新 |
| 0x1F010 | FC_FATX_PROCESS_FDT_ERROR | FATX处理FDT错误 | FDT处理 |

### USB磁盘格式化错误码 (0x1200 系列)

| 错误码 | 错误名称 | 中文描述 | 操作类型 |
|--------|----------|----------|----------|
| 0x1201 | ERROR_INCOMPATIBLE_FS | 不兼容的文件系统 | 文件系统兼容性 |
| 0x1202 | ERROR_CANT_QUICK_FORMAT | 不能快速格式化 | 快速格式化 |
| 0x1203 | ERROR_INVALID_CLUSTER_SIZE | 无效的簇大小 | 簇大小 |
| 0x1204 | ERROR_INVALID_VOLUME_SIZE | 无效的卷大小 | 卷大小 |
| 0x1205 | ERROR_CANT_START_THREAD | 不能启动线程 | 线程启动 |
| 0x1206 | ERROR_BADBLOCKS_FAILURE | 坏块检测失败 | 坏块检测 |
| 0x1207 | ERROR_ISO_SCAN | ISO扫描错误 | ISO处理 |
| 0x1208 | ERROR_ISO_EXTRACT | ISO提取错误 | ISO提取 |
| 0x1209 | ERROR_CANT_REMOUNT_VOLUME | 不能重新挂载卷 | 卷挂载 |
| 0x120A | ERROR_CANT_PATCH | 不能打补丁 | 补丁应用 |
| 0x120B | ERROR_CANT_ASSIGN_LETTER | 不能分配驱动器号 | 驱动器号 |
| 0x120C | ERROR_CANT_MOUNT_VOLUME | 不能挂载卷 | 卷挂载 |
| 0x120D | ERROR_BAD_SIGNATURE | 错误的签名 | 签名验证 |
| 0x120E | ERROR_CANT_DOWNLOAD | 不能下载 | 下载操作 |

### TBC云错误码 (TBCE系列)

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| TBCE_SUCCESS | TBCE_SUCCESS | 成功 | 成功 |
| TBCE_FALSE | TBCE_FALSE | 失败 | 通用错误 |
| TBCE_PARAMETER | TBCE_PARAMETER | 参数错误 | 参数错误 |
| TBCE_NO_API | TBCE_NO_API | 没有API | API错误 |
| TBCE_NO_MEM | TBCE_NO_MEM | 内存不足 | 内存错误 |
| TBCE_NOT_INIT | TBCE_NOT_INIT | 未初始化 | 初始化错误 |
| TBCE_NET | TBCE_NET | 网络错误 | 网络错误 |
| TBCE_LOGIN | TBCE_LOGIN | 登录错误 | 认证错误 |
| TBCE_OPENFILE | TBCE_OPENFILE | 打开文件错误 | 文件错误 |
| TBCE_FILE_TOO_LONG | TBCE_FILE_TOO_LONG | 文件过长 | 文件错误 |
| TBCE_FILE_READ | TBCE_FILE_READ | 文件读取错误 | 文件错误 |
| TBCE_FILE_SEND | TBCE_FILE_SEND | 文件发送错误 | 文件传输 |
| TBCE_FILE_FILE_EXIST | TBCE_FILE_FILE_EXIST | 文件已存在 | 文件错误 |
| TBCE_NOT_USER | TBCE_NOT_USER | 非用户 | 权限错误 |
| TBCE_NO_ITEM | TBCE_NO_ITEM | 没有项目 | 数据错误 |
| TBCE_FILE_WRITE | TBCE_FILE_WRITE | 文件写入错误 | 文件错误 |
| TBCE_FILE_SPLIT | TBCE_FILE_SPLIT | 文件分割错误 | 文件处理 |
| TBCE_ITEM_EXIST | TBCE_ITEM_EXIST | S3云文件已存在，认为正常 | 云存储 |
| TBCE_CANCEL | TBCE_CANCEL | 取消操作 | 用户操作 |

### TBC云业务错误码

| 错误码 | 错误名称 | 中文描述 | HTTP状态码 |
|--------|----------|----------|------------|
| TBCE_CLOUD_ERROR_TASK_NOT_EXIST | 任务不存在 | taskId is not exist | 11001 |
| TBCE_CLOUD_ERROR_BACKUP_NOT_ESIT | 备份不存在 | backupId is not exist | 11002 |
| TBCE_CLOUD_ERROR_FILE_NOT_FOUND | 文件未找到 | this file name is not exist | 11003 |
| TBCE_CLOUD_ERROR_USER_MISMATCH | 用户不匹配 | backup and user mismatch | 11004 |
| TBCE_CLOUD_ERROR_NOT_USER_PATH | 非用户路径 | this path is not own to this user | 11005 |
| TBCE_CLOUD_ERROR_PKG_NOT_RIGHT | 包文件参数错误 | pkg file params is not right | 11006 |
| TBCE_CLOUD_ERROR_LACK_SPACE | 空间不足 | Lack of space | 11007 |
| TBCE_CLOUD_ERROR_PATH_NOT_FOUND | 路径不存在 | this pak path is not exist | 11008 |
| TBCE_CLOUD_ERROR_NO_TOKEN | 缺少令牌 | token is need | 11009 |
| TBCE_CLOUD_ERROR_INVALID_USER | 用户无效 | user is not valid users | 11010 |
| TBCE_CLOUD_ERROR_INVALID_PARS | 请求参数错误 | Incorrect request parameters | 11012 |
| TBCE_CLOUD_ERROR_BACKUP_FAIL | 备份失败 | backup is error! | 11013 |
| TBCE_CLOUD_ERROR_PATH_NOT_CONTAIN | 路径包含非法字符 | this is path can not contail / .. or .. | 11014 |

### FTP错误码 (UTE系列)

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| UTE_SUCCESS | UTE_SUCCESS | 成功 | 成功 |
| UTE_ERROR | UTE_ERROR | 错误 | 通用错误 |
| UTE_CONNECT_FAILED | UTE_CONNECT_FAILED | 连接失败 | 连接错误 |
| UTE_CONNECT_REJECTED | UTE_CONNECT_REJECTED | 连接被拒绝 | 连接错误 |
| UTE_CONNECT_TERMINATED | UTE_CONNECT_TERMINATED | 连接终止 | 连接错误 |
| UTE_CONNECT_TIMEOUT | UTE_CONNECT_TIMEOUT | 连接超时 | 超时错误 |
| UTE_NOCONNECTION | UTE_NOCONNECTION | 无连接 | 连接错误 |
| UTE_NAME_LOOKUP_FAILED | UTE_NAME_LOOKUP_FAILED | 名称查找失败 | DNS错误 |
| UTE_DATAPORT_FAILED | UTE_DATAPORT_FAILED | 数据端口失败 | 端口错误 |
| UTE_ACCEPT_FAILED | UTE_ACCEPT_FAILED | 接受连接失败 | 连接错误 |
| UTE_SVR_REQUEST_DENIED | UTE_SVR_REQUEST_DENIED | 服务器拒绝请求 | 服务器错误 |
| UTE_SVR_NOT_SUPPORTED | UTE_SVR_NOT_SUPPORTED | 服务器不支持 | 服务器错误 |
| UTE_SVR_NO_RESPONSE | UTE_SVR_NO_RESPONSE | 服务器无响应 | 服务器错误 |
| UTE_SVR_ACCESS_DENIED | UTE_SVR_ACCESS_DENIED | 服务器拒绝访问 | 权限错误 |
| UTE_SVR_DATA_CONNECT_FAILED | UTE_SVR_DATA_CONNECT_FAILED | 服务器数据连接失败 | 数据传输 |
| UTE_MAIL_FAILED | UTE_MAIL_FAILED | 邮件操作失败 | 邮件错误 |
| UTE_RETR_FAILED | UTE_RETR_FAILED | 检索失败 | 数据传输 |
| UTE_PORT_FAILED | UTE_PORT_FAILED | 端口操作失败 | 端口错误 |
| UTE_LIST_FAILED | UTE_LIST_FAILED | 列表操作失败 | 文件操作 |
| UTE_STOR_FAILED | UTE_STOR_FAILED | 存储操作失败 | 文件操作 |
| UTE_DATA_FAILED | UTE_DATA_FAILED | 数据操作失败 | 数据传输 |
| UTE_USER_FAILED | UTE_USER_FAILED | 用户验证失败 | 认证错误 |
| UTE_PASS_FAILED | UTE_PASS_FAILED | 密码验证失败 | 认证错误 |
| UTE_OUT_OF_MEMORY | UTE_OUT_OF_MEMORY | 内存不足 | 内存错误 |
| UTE_ABORTED | UTE_ABORTED | 操作中止 | 用户操作 |
| UTE_BAD_HOSTNAME | UTE_BAD_HOSTNAME | 主机名错误 | 网络错误 |
| UTE_INVALID_ADDRESS | UTE_INVALID_ADDRESS | 地址无效 | 网络错误 |
| UTE_USER_TERMINATED | UTE_USER_TERMINATED | 用户终止 | 用户操作 |

### ESE数据库错误码 (Exchange相关)

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| 0xC8000262L | hrLogfileHasBadSignature | 日志文件签名错误 | 日志文件错误 |
| 0xC8000263L | hrLogFileNotContiguous | 日志文件不连续 | 日志文件错误 |
| 0x000003f3L | hrRegNotFind | 注册表项未找到 | 注册表错误 |

### 通用还原错误码 (Universal Restore)

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| 0x02B1 | ERROR_USLRESTORE_INVALID_PARAMETER | 无效参数 | 参数错误 |
| 0x02B2 | ERROR_USLRESTORE_MALLOC_ERROR | 内存分配错误 | 内存错误 |
| 0x02B3 | ERROR_USLRESTORE_INTER_ERROR | 内部错误 | 内部错误 |
| 0x02B4 | ERROR_USLRESTORE_SYSTEM_ERROR | 系统错误 | 系统错误 |
| 0x02B5 | ERROR_USLRESTORE_EXCEPTIONAL | 异常错误 | 异常处理 |
| 0x02B6 | ERROR_USLRESTORE_PRIVILEGES | 权限错误 | 权限错误 |
| 0x02B7 | ERROR_USLRESTORE_LOADDESTSYSREGEDIT | 加载目标系统注册表错误 | 注册表错误 |
| 0x02B8 | ERROR_USLRESTORE_READREGEDITVALUE | 读取注册表值错误 | 注册表错误 |
| 0x02B9 | ERROR_USLRESTORE_INVALID_CLASSMEMBERPARAMETER | 无效类成员参数 | 参数错误 |
| 0x02BA | ERROR_USLRESTORE_OPENREGEDIT_ERROR | 打开注册表错误 | 注册表错误 |
| 0x02BB | ERROR_USLRESTORE_OPENHAL_ERROR | 打开HAL错误 | 硬件抽象层错误 |
| 0x02BC | ERROR_USLRESTORE_HALMATCHID_ERROR | HAL匹配ID错误 | 硬件抽象层错误 |
| 0x02BD | ERROR_USLRESTORE_ONFINDVALUEINREGEDIT | 在注册表中查找值失败 | 注册表错误 |
| 0x02BE | ERROR_USLRESTORE_NOENOUGHMEMORY | 内存不足 | 内存错误 |
| 0x02BF | ERROR_USLRESTORE_FINDFILEINFORDRIVERS | 查找驱动文件失败 | 驱动程序错误 |
| 0x02C0 | ERROR_USLRESTORE_OPENINFCLOSEINFFILE | 打开/关闭INF文件错误 | 文件错误 |
| 0x02C1 | ERROR_USLRESTORE_DREATEDELETREGEDITEKEY | 创建/删除注册表键错误 | 注册表错误 |
| 0x02C2 | ERROR_USLRESTORE_WINDOWSAPIERROR | Windows API错误 | API错误 |
| 0x02C3 | ERROR_USLRESTORE_OPERATIONINFFILE | 操作INF文件错误 | 文件错误 |
| 0x02C4 | ERROR_USLRESTORE_OSISNEWOS | 操作系统是新OS | 系统兼容性 |
| 0x02C5 | ERROR_USLRESTORE_COPYFILEERROR | 复制文件错误 | 文件操作 |
| 0x02C6 | ERROR_USLRESTORE_NOFINDFILEANDPATH | 找不到文件和路径 | 路径错误 |
| 0x02C7 | ERROR_USLRESTORE_CREATESID | 创建SID错误 | 安全标识符错误 |
| 0x02C8 | ERROR_USLRESTORE_SETREGEDITACCESS | 设置注册表访问权限错误 | 权限错误 |
| 0x02C9 | ERROR_USLRESTORE_OPENPTORDISK | 打开分区或磁盘错误 | 磁盘访问错误 |
| 0x02CA | ERROR_USLRESTORE_IOCTL_ERROR | IOCTL错误 | 设备控制错误 |
| 0x02CB | ERROR_USLRESTORE_READWRITEDISK | 读写磁盘错误 | 磁盘IO错误 |
| 0x02CC | ERROR_USLRESTORE_BOOTINIERROR | Boot.ini错误 | 引导配置错误 |
| 0x02CD | ERROR_USLRESTORE_BOOTININOFINDPT | Boot.ini中找不到分区 | 引导配置错误 |
| 0x02CE | ERROR_USLRESTORE_INVALIDMBRORPT | 无效MBR或分区表 | 分区表错误 |
| 0x02CF | ERROR_USLRESTORE_OUTINVALID_PARAMETER | 输出无效参数 | 参数错误 |
| 0x02D0 | ERROR_USLRESTORE_OPTYPE_ERROR | 操作类型错误 | 操作错误 |
| 0x02D1 | ERROR_USLRESTORE_USERCANCEL | 用户取消 | 用户操作 |
| 0x02D2 | ERROR_USLRESTORE_NOHAVEDRV | 没有驱动器 | 驱动程序错误 |
| 0x02D3 | ERROR_USLRESTORE_REGSECURITY | 注册表安全性错误 | 安全错误 |
| 0x02D4 | ERROR_MULTIPLE_CONNECTIONS | 多重连接错误 | 连接错误 |

### FAT转NTFS错误码 (0xFE000 系列)

| 错误码 | 错误名称 | 中文描述 | 转换阶段 |
|--------|----------|----------|----------|
| 0xFE001 | CNVFAT_ERROR_INVALID_PARTITION | 无效分区 | 分区验证 |
| 0xFE002 | CNVFAT_ERROR_CHECK_PARTITION | 检查分区错误 | 分区检查 |
| 0xFE004 | CNVFAT_ERROR_INSUFFICIENT_SPACE | 空间不足 | 空间检查 |
| 0xFE008 | CNVFAT_ERROR_INVALID_FILESYSTEM | 无效文件系统 | 文件系统检查 |
| 0xFE010 | CNVFAT_ERROR_CANNOT_CREATE_PROC | 不能创建进程 | 进程创建 |
| 0xFE020 | CNVFAT_ERROR_STATUS | 状态错误 | 状态检查 |
| 0xFE040 | CNVFAT_ERROR_CANNOT_LOCK_DRIVE | 不能锁定驱动器 | 驱动器锁定 |
| 0xFE080 | CNVFAT_ERROR_HIDDEN_PARTITION | 隐藏分区 | 隐藏分区处理 |

### 系统快照错误码 (XSnapshot)

| 错误码 | 错误名称 | 中文描述 | 操作类型 |
|--------|----------|----------|----------|
| 0x0380 | BP_ERR_XSNAPSHOT_INIT | 初始化快照失败 | 初始化 |
| 0x0381 | BP_ERR_XSNAPSHOT_CREATE_SNAPSHOT | 创建还原点失败 | 快照创建 |
| 0x0382 | BP_ERR_XSNAPSHOT_DELETE_SNAPSHOT | 删除还原点失败 | 快照删除 |
| 0x0383 | BP_ERR_XSNAPSHOT_UNINSTALL | 卸载快照失败 | 快照卸载 |
| 0x0384 | BP_ERR_XSNAPSHOT_RESTORE | 还原失败 | 快照还原 |
| 0x0385 | BP_ERR_XSNAPSHOT_OPEN_DISK | 打开磁盘失败 | 磁盘操作 |
| 0x0386 | BP_ERR_XSNAPSHOT_OPEN_VOLUME | 打开卷失败 | 卷操作 |
| 0x0387 | BP_ERR_XSNAPSHOT_ADD_DISK | 添加磁盘失败 | 磁盘管理 |
| 0x0388 | BP_ERR_XSNAPSHOT_ADD_VOLUME | 添加卷失败 | 卷管理 |
| 0x0389 | BP_ERR_XSNAPSHOT_DELETE_DISK | 删除快照磁盘失败 | 磁盘管理 |
| 0x038A | BP_ERR_XSNAPSHOT_DELETE_VOLUME | 删除快照卷失败 | 卷管理 |

### XSnapshot SDK详细错误码

| 错误码 | 错误名称 | 中文描述 | 技术细节 |
|--------|----------|----------|----------|
| 0x0390 | BP_ERR_XSNAPSHOT_SDK_BASE | 内部错误 | SDK基础错误 |
| 0x0391 | BP_ERR_XSNAPSHOT_SDK_OPENFILE | 打开文件失败 | 文件访问错误 |
| 0x0392 | BP_ERR_XSNAPSHOT_SDK_MEMORY | 分配内存失败 | 内存分配错误 |
| 0x0393 | BP_ERR_XSNAPSHOT_SDK_NEED_DEFRAG | 需要磁盘整理 | 磁盘碎片过多 |
| 0x0394 | BP_ERR_XSNAPSHOT_SDK_GETFILESIZE | 获取文件大小失败 | 文件信息错误 |
| 0x0395 | BP_ERR_XSNAPSHOT_SDK_READ | 读取文件失败 | 文件读取错误 |
| 0x0396 | BP_ERR_XSNAPSHOT_SDK_NOT_FIXED | 没有修复设备卷 | 卷修复错误 |
| 0x0397 | BP_ERR_XSNAPSHOT_SDK_IOCTL | 磁盘碎片太多 | 设备控制错误 |
| 0x0398 | BP_ERR_XSNAPSHOT_SDK_NOT_SINGLE_DISK | 指定的卷不是在本地硬盘中 | 磁盘类型错误 |
| 0x0399 | BP_ERR_XSNAPSHOT_SDK_UNKNOWN_PT | 未知分区格式 | 分区类型错误 |
| 0x039A | BP_ERR_XSNAPSHOT_SDK_WRITE | 写入文件失败 | 文件写入错误 |
| 0x039B | BP_ERR_XSNAPSHOT_SDK_INSTALL_DRIVER | 复制驱动文件失败 | 驱动安装错误 |
| 0x039C | BP_ERR_XSNAPSHOT_SDK_MBR_INSTALLED | 系统快照的引导程序已经安装 | MBR状态 |
| 0x039D | BP_ERR_XSNAPSHOT_SDK_MBR_BAD | 无效MBR | MBR错误 |
| 0x039E | BP_ERR_XSNAPSHOT_SDK_INTERNAL | 磁盘碎片太多，或者虚拟保护文件太大 | 内部处理错误 |
| 0x039F | BP_ERR_XSNAPSHOT_SDK_GET_DISK_INFO | 获取磁盘大小失败 | 磁盘信息错误 |
| 0x03A0 | BP_ERR_XSNAPSHOT_SDK_DISK_ERROR | 磁盘分区错误 | 分区错误 |
| 0x03A1 | BP_ERR_XSNAPSHOT_SDK_DISK_NO_3F | 第一个分区前的保留空间小于63个扇区 | 分区对齐错误 |
| 0x03A2 | BP_ERR_XSNAPSHOT_SDK_NO_FREE_BLOCK | 磁盘碎片太多 | 磁盘碎片错误 |
| 0x03A3 | BP_ERR_XSNAPSHOT_SDK_NOT_FIND_BLOCK | 找不到模块 | 模块查找错误 |
| 0x03A4 | BP_ERR_XSNAPSHOT_SDK_MANY_BLOCKS | 模块过多 | 模块数量错误 |
| 0x03A5 | BP_ERR_XSNAPSHOT_SDK_XSSFS | 内部文件系统错误 | 文件系统错误 |
| 0x03A6 | BP_ERR_XSNAPSHOT_SDK_PT_PROTECTED | 被保护的分区 | 分区保护错误 |
| 0x03A7 | BP_ERR_XSNAPSHOT_SDK_PT_MAX | 受保护分区数已经达到最大值 | 分区数量限制 |
| 0x03A8 | BP_ERR_XSNAPSHOT_SDK_PT_NOT_FIND | 没有找到分区 | 分区查找错误 |
| 0x03A9 | BP_ERR_XSNAPSHOT_SDK_DEL_PT_WITH_RP | 内部错误 | 分区删除错误 |
| 0x03AA | BP_ERR_XSNAPSHOT_SDK_DRV_NOT_EXIST | 没有足够空间保存虚拟保护文件 | 存储空间错误 |
| 0x03AB | BP_ERR_XSNAPSHOT_SDK_PASSWORD | 密码错误 | 密码验证错误 |
| 0x03AC | BP_ERR_XSNAPSHOT_SDK_LOCK_FAIL | 锁定磁盘失败 | 磁盘锁定错误 |
| 0x03AD | BP_ERR_XSNAPSHOT_SDK_CREATE_RP | 磁盘正忙，锁定磁盘失败 | 还原点创建错误 |
| 0x03AE | BP_ERR_XSNAPSHOT_SDK_NOT_FIND_PT | 未找到分区 | 分区查找错误 |
| 0x03AF | BP_ERR_XSNAPSHOT_SDK_DEL_RP | 删除还原点失败 | 还原点删除错误 |
| 0x03B0 | BP_ERR_XSNAPSHOT_SDK_DYN_DISK | 不支持动态磁盘 | 动态磁盘错误 |
| 0x03B1 | BP_ERR_XSNAPSHOT_RP_NUM_NULL | 没有还原点 | 还原点数量错误 |
| 0x03B2 | BP_ERR_XSNAPSHOT_GET_SYSTEM_DISK_FAIL | 无法获取被保护的系统磁盘的快照点 | 系统盘快照错误 |

### 引导盘/应急盘错误码

| 错误码 | 错误名称 | 中文描述 | 错误原因 |
|--------|----------|----------|----------|
| 0x03C0 | BP_ERR_BOOT_DISK_TYPE | 系统分区或引导分区在动态磁盘或GPT磁盘上 | 磁盘类型不支持 |
| 0x03C1 | BP_ERR_BOOT_CLUSER_SIZE | 目标分区的簇大小不支持制作启动盘 | 簇大小不兼容 |
| 0x03C2 | BP_ERR_BOOT_DEV_IS_READ_ONLY | 只读设备，无法安装 | 设备只读 |
| 0x03C3 | BP_ERR_BOOT_SECTOR_SIZE | 不支持的扇区大小，无法安装 | 扇区大小不支持 |
| 0x03C4 | BP_ERR_BOOT_ASSIGN_VOL_LETTER | 分配驱动号失败 | 驱动器号分配错误 |
| 0x03C5 | BP_ERR_BOOT_NEED_PARTED | 需要对目标磁盘进行分区和格式化 | 磁盘未分区 |
| 0x03C6 | BP_ERR_BOOT_NEED_FORMAT | 需要格式化，不支持的文件系统或分区没有被格式化 | 格式化需求 |
| 0x03C7 | BP_ERR_BOOT_NO_PARTITION | 目标磁盘上没有分区或活动分区 | 缺少分区 |
| 0x03C8 | BP_ERR_BOOT_TYPE_UNKNOWN | 不能识别该系统分区 | 系统分区未识别 |
| 0x03CA | BP_ERR_BOOT_GET_SPACE | 获取磁盘空间或卷空间失败 | 空间信息获取错误 |
| 0x03CB | BP_ERR_BOOT_LOCKED_BITLOCKER | 不支持Bitlocker分区 | Bitlocker加密 |
| 0x03CC | BP_ERR_BOOT_ACCESS_DENIED | 系统分区或目标分区不可写或不可访问 | 访问权限错误 |
| 0x03CD | BP_ERR_NO_FOUND_CDROM_LETTER | 找不到可用的CD-ROM驱动器 | 光驱不可用 |
| 0x03CE | BP_ERR_BOOT_VHD_DISK | 系统分区或引导分区在VHD磁盘上 | VHD磁盘不支持 |

### SQL Server备份错误码 (0x0B00 系列)

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| 0x0B01 | BP_ERR_JSON_CONTENT | 操作失败，请重启程序后再试 | JSON处理错误 |
| 0x0B02 | BP_ERR_NO_SQL | 没有检测到任何SQL实例 | SQL实例错误 |
| 0x0B03 | BP_ERR_SQL_NO_VSS | 没有安装SQL Server VSS Writer服务程序 | VSS服务错误 |
| 0x0B04 | BP_ERR_SQL_CREDENTIAL_FAIL | 实例授权失败 | 权限验证错误 |
| 0x0B05 | BP_ERR_SQL_SERVICE_STOP | 实例的服务程序状态不正确 | 服务状态错误 |
| 0x0B06 | BP_ERR_SQL_VERTOOLOW | 本产品只支持SQL2005及以上的SQL版本 | 版本不支持 |
| 0x0B07 | BP_ERR_SQL_NOSERVER | 没有找到SQL实例的服务程序 | 服务程序未找到 |
| 0x0B10 | BP_ERR_SQL_STARTSERVER_FAIL | 无法打开SQL服务 | 服务启动错误 |
| 0x0B11 | BP_ERR_SQL_QUERYSERVICESTATUES_FAIL | 无法查询SQL服务状态 | 服务状态查询错误 |
| 0x0B12 | BP_ERR_SQL_SERVICE_RUNING | 实例的服务程序正在运行 | 服务状态冲突 |
| 0x0B13 | BP_ERR_SQL_ENUMINS_FAIL | 无法枚举SQL实例 | 实例枚举错误 |
| 0x0B14 | BP_ERR_SQL_SMOINIT_FAIL | .Net版本过低，请安装.Net 4.0或4.0以上版本 | .NET版本错误 |
| 0x0B15 | BP_ERR_SQL_WINDOWSLOGIN_FAIL | 以Windows身份验证方式登录数据库失败 | Windows认证错误 |
| 0x0B16 | BP_ERR_SQL_SQLLOGIN_FAIL | 以SQL Server身份验证方式登录数据库失败 | SQL认证错误 |
| 0x0B17 | BP_ERR_SQL_ENUMDBS_FAIL | 枚举数据库失败 | 数据库枚举错误 |
| 0x0B18 | BP_ERR_SQL_GETDBSINFO_FAIL | 无法获取数据库信息 | 数据库信息错误 |
| 0x0B19 | BP_ERR_SQL_SETPARA_FAIL | 操作失败，请重启程序后再试 | 参数设置错误 |
| 0x0B1A | BP_ERR_SQL_NOTSETPARA | 操作失败，请重启程序后再试 | 参数未设置错误 |
| 0x0B1B | BP_ERR_SQL_REFRESHDATA_FAIL | 无法将数据库数据刷新到数据库文件中 | 数据刷新错误 |
| 0x0B1C | BP_ERR_SQL_BREAKLOG_FAIL | 无法对数据库进行日志截断操作 | 日志截断错误 |
| 0x0B1D | BP_ERR_SQL_GETJSONDATA_FAIL | 操作失败，请重启程序后再试 | JSON数据获取错误 |
| 0x0B1E | BP_ERR_SQL_BACKINSNOEXIST | 备份的实例不存在 | 备份实例不存在 |
| 0x0B1F | BP_ERR_SQL_CREDENTIAL_OVERDUE | 实例授权信息过期 | 授权信息过期 |
| 0x0B20 | BP_ERR_SQL_NOCREDENTIAL | 实例没有授权信息 | 缺少授权信息 |
| 0x0B31 | BP_ERR_SQL_SRC_NOTENOUGH_SPACE | 数据库文件所在分区空间不足，不能启动VSS | 存储空间不足 |
| 0x0B32 | BP_ERR_SQL_VSS_TIMEOUT | 启动VSS超时，数据库持续访问中 | VSS超时 |
| 0x0B3A | BP_ERR_SQL_INSSINGLEMODE | 实例处于单用户模式 | 单用户模式错误 |
| 0x0B40 | BP_ERR_SQL_INSTANCE_NOT_FOUND | 没有找到需要备份的实例 | 实例未找到 |
| 0x0B41 | BP_ERR_SQL_PERMISSION_NOTENOUGH | 获取数据库信息失败,权限不足 | 权限不足 |

### Android备份错误码 (0x0930 系列)

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| 0x0931 | BP_ERR_NO_ANDROID_DATA | 没有要备份的数据 | 数据为空 |
| 0x0932 | BP_ERR_BACKUP_ANDROID_CONTACTS | 备份联系人失败 | 联系人备份错误 |
| 0x0933 | BP_ERR_BACKUP_ANDROID_SMS | 备份短信失败 | 短信备份错误 |
| 0x0934 | BP_ERR_BACKUP_ANDROID_CALL_LOG | 备份录音失败 | 通话记录备份错误 |
| 0x0935 | BP_ERR_BACKUP_ANDROID_FILE | 备份文件失败 | 文件备份错误 |
| 0x0936 | BP_ERR_BACKUP_ANDROID_BASIC_DATA | 备份数据失败 | 基础数据备份错误 |
| 0x0937 | BP_ERR_BACKUP_ANDROID | 安卓备份失败 | Android备份错误 |
| 0x0938 | BP_ERR_INIT_ANDROID | 连接安卓设备失败 | 设备连接错误 |
| 0x0939 | BP_ERR_RESTORE_ANDROID_PART_OK | 成功恢复安卓设备里的部分数据 | 部分还原成功 |
| 0x093A | BP_ERR_RESTORE_ANDROID_CONTACTS | 恢复联系人失败 | 联系人还原错误 |
| 0x093B | BP_ERR_RESTORE_ANDROID_SMS | 恢复短信失败 | 短信还原错误 |
| 0x093C | BP_ERR_RESTORE_ANDROID_CALL_LOG | 恢复录音失败 | 通话记录还原错误 |
| 0x093D | BP_ERR_RESTORE_ANDROID_FILE | 恢复文件失败 | 文件还原错误 |
| 0x0953 | BP_ERR_GET_ANDROID_INFO | 无法获得安卓设备信息 | 设备信息获取错误 |
| 0x0954 | BP_ERR_RESTORE_ANDROID_FAIL | 安卓恢复失败 | Android还原错误 |
| 0x0955 | BP_ERR_ANDROID_CONNECT_FAIL | 连接安卓设备失败 | 设备连接错误 |
| 0x0958 | BP_ERR_NOT_DEBUG_MODE | 请先打开设备里的USB调试模式 | USB调试模式错误 |
| 0x0959 | BP_ERR_ALLOW_PUSH_APP | EaseUS Todo Backup安装失败 | 应用安装错误 |
| 0x095A | BP_ERR_NO_ANDROID_DEVICE | 没有找到安卓设备 | 设备未找到 |
| 0x095B | BP_ERR_IS_OLD_APK_VERSION | 所安装的EaseUS Todo Backup版本太旧 | 版本过旧 |
| 0x095C | BP_ERR_ANDROID_NO_SPACE | 因设备里的空间不足，安装EaseUS Todo Backup失败 | 存储空间不足 |

### PXE网络启动错误码

| 错误码 | 错误名称 | 中文描述 | 错误类型 |
|--------|----------|----------|----------|
| 0x0613 | BP_ERR_PXE_ALREADY_START | PXE服务已经启动 | 服务状态错误 |
| 0x0614 | BP_ERR_PORT_67 | 端口67正在被其他进程使用 | 端口占用错误 |
| 0x0615 | BP_ERR_PORT_68 | 端口68正在被其他进程使用 | 端口占用错误 |
| 0x0616 | BP_ERR_PORT_69 | 端口69正在被其他进程使用 | 端口占用错误 |

## 错误码组合规律分析

### 1. 组合型错误码结构
某些错误码采用组合形式，如 0x0000F003 实际包含两个可能的含义：
- f000f003 (FAT_CHECK_FILE_SYSTEM_ERROR) = 0xF000 + 0x0003
- f001f003 (FC_CHECK_FAT_NEQ_FATX) = 0x1F000 + 0x0003

### 2. 基础码规律
- **BP_ERR_BASE**: 动态计算，包含行号和模块号信息 `(__LINE__<<20) | BP_ERR_MODE`
- **FAT_ERROR_BASE**: 0xF000
- **FC_BASE**: 0x1F000 (FAT Copy)
- **NTFS错误**: 0xF0000000 起始
- **TBCE_BASE**: 使用 `TBCE_MAKE(code)` 宏，格式为 `__LINE__ << 16 | (code)`

### 3. 模块识别规律
- **0x0000-0x03FF**: 基础系统错误
- **0x0200xxxx**: 网络通信模块 (BP_ERR_BASE + BP_ERR_BASE200 + offset)
- **0x02B0-0x02D4**: Universal Restore模块
- **0x0380-0x03BF**: XSnapshot系统快照模块
- **0x03C0-0x03FF**: 引导盘/应急盘模块
- **0x0B00-0x0B41**: SQL Server备份模块
- **0x0930-0x095C**: Android备份模块
- **0x0613-0x0616**: PXE网络启动模块
- **0xF000xxxx**: FAT文件系统模块
- **0x1F000xxx**: FAT拷贝模块
- **0xF0000xxx**: NTFS文件系统模块
- **0x1200xxxx**: USB格式化模块
- **0xFE00xxxx**: FAT转NTFS模块
- **TBCE_xxxxx**: Todo Backup Cloud模块
- **UTE_xxxxx**: FTP客户端模块
- **0xC8000xxx**: Exchange ESE数据库模块

### 4. 错误码生成机制
```cpp
// 基础错误码生成
#define BP_ERR_BASE   (((__LINE__)<<20) | BP_ERR_MODE)
#define BP_ERR_NETMANAGER_NULL (BP_ERR_BASE + BP_ERR_BASE200 + 0x0001)

// TBC云错误码生成  
#define TBCE_MAKE(code) ( __LINE__ << 16 | (code) )
#define TBCE_FALSE      TBCE_MAKE(1)

// FAT错误码生成
#define FAT_ERROR_BASE  0xF000
#define FAT_CHECK_FILE_SYSTEM_ERROR (FAT_ERROR_BASE+3)

// 扩展错误码组合
#define FAT_CHECK_EXT_ERROR_FAT1_FAT2  354 - 3
// 最终错误码: FAT_CHECK_FILE_SYSTEM_ERROR + FAT_CHECK_EXT_ERROR_FAT1_FAT2
```

### 5. 错误码优先级分类
- **致命错误**: 系统崩溃、内存不足、设备故障
- **严重错误**: 文件系统损坏、磁盘错误、网络中断
- **警告错误**: 权限不足、文件不存在、参数无效
- **信息错误**: 用户取消、操作成功、状态通知

## 错误码查询指南

### 快速定位错误类型
1. **查看前缀**: 根据错误码前缀确定模块
   - `0x0000F003` → 可能是FAT文件系统(f000f003)或FAT拷贝(f001f003)
   - `0x02xx` → 网络通信模块
   - `0x03xx` → 系统快照、引导盘模块
   - `0x0Bxx` → SQL Server备份模块
   - `TBCE_` → Todo Backup Cloud模块
   - `UTE_` → FTP客户端模块

2. **查找基础码**: 减去基础码得到具体错误编号
3. **检查组合**: 某些错误码可能有多重含义
4. **参考上下文**: 结合操作上下文确定具体含义

### 常见错误码快速参考

#### 文件系统相关
- **0x0000F003**: FAT文件系统检查错误或FAT拷贝时FAT表不匹配
- **0xF0000002**: NTFS写扇区错误  
- **0xF0000003**: NTFS读扇区错误
- **0x1F003**: FAT拷贝时FAT与FATX不相等
- **0xFE001**: FAT转NTFS时分区无效

#### USB和磁盘操作
- **0x1201**: USB格式化时文件系统不兼容
- **0x1202**: USB不能快速格式化
- **0x1203**: USB无效的簇大小
- **0x120A**: USB不能打补丁

#### 系统快照相关
- **0x0380**: 初始化快照失败
- **0x0381**: 创建还原点失败
- **0x0393**: 需要磁盘整理(磁盘碎片过多)
- **0x03AB**: 快照密码错误

#### 网络和通信
- **0x0201**: 网络通信对象指针为空
- **0x0207**: 异步命令超时
- **UTE_CONNECT_FAILED**: FTP连接失败
- **UTE_SVR_ACCESS_DENIED**: FTP服务器拒绝访问

#### 数据库备份
- **0x0B02**: 没有检测到任何SQL实例
- **0x0B04**: SQL实例授权失败
- **0x0B14**: .Net版本过低

#### Android备份
- **0x0931**: 没有要备份的Android数据
- **0x0958**: 请先打开USB调试模式
- **0x095A**: 没有找到安卓设备

#### 云备份相关
- **TBCE_LOGIN**: 云备份登录错误
- **TBCE_CLOUD_ERROR_LACK_SPACE**: 云存储空间不足
- **TBCE_CLOUD_ERROR_INVALID_USER**: 云用户无效

### 错误码分析步骤
1. **确定错误码格式**: 
   - 十六进制数字 → 查找对应模块表
   - 字符串前缀 → 查找对应枚举定义
   
2. **定位错误模块**:
   - 根据前缀或数值范围确定所属模块
   - 参考模块识别规律表
   
3. **查找具体错误**:
   - 在对应模块表中查找错误定义
   - 注意组合型错误码的多重含义
   
4. **分析错误上下文**:
   - 结合当前操作确定具体含义
   - 参考可能原因和建议操作

### 错误处理建议

#### 按严重程度处理
- **致命错误**: 立即停止操作，检查系统状态
- **严重错误**: 尝试恢复操作，记录详细日志  
- **警告错误**: 提示用户，允许继续或重试
- **信息错误**: 记录状态，正常继续流程

#### 常见错误处理策略
1. **内存不足**: 释放资源，减少并发操作
2. **权限错误**: 提升权限或更改用户账户
3. **网络错误**: 检查连接，重试机制
4. **磁盘错误**: 检查磁盘健康，运行磁盘检查
5. **文件系统错误**: 运行文件系统检查和修复

## 备注

- 此文档基于代码中的实际定义生成，所有错误码和描述信息均来源于工程源码
- 错误码的具体含义可能因模块和上下文而异
- 建议在排查问题时结合日志和操作上下文进行分析
- 定期更新此文档以保持与代码的同步

## 统计信息

### 错误码总数统计
- **基础错误码**: 约60个 (0x0000-0x03FF系列)
- **FAT文件系统错误码**: 约50个 (0xF000系列)
- **NTFS文件系统错误码**: 约40个 (0xF0000000系列)  
- **网络通信错误码**: 约30个 (0x0200系列)
- **FAT拷贝错误码**: 约16个 (0x1F000系列)
- **USB格式化错误码**: 约14个 (0x1200系列)
- **系统快照错误码**: 约50个 (0x0380-0x03BF系列)
- **SQL备份错误码**: 约65个 (0x0B00系列)
- **Android备份错误码**: 约30个 (0x0930系列)
- **TBC云错误码**: 约35个 (TBCE系列)
- **FTP错误码**: 约80个 (UTE系列)
- **通用还原错误码**: 约36个 (0x02B0系列)
- **其他专项错误码**: 约50个

**总计**: 超过500个错误码定义

### 模块覆盖范围
- 文件系统操作 (FAT, NTFS, ExFAT, Ext, ReFS)
- 磁盘和分区管理
- 网络通信和FTP传输
- 数据库备份 (SQL Server, Exchange)
- 移动设备备份 (Android)
- 云存储服务
- 系统快照和还原
- 引导盘制作
- 虚拟机操作
- 设备驱动管理

### 错误码设计特点
1. **分层架构**: 采用模块化分层设计，便于维护和扩展
2. **动态生成**: 部分错误码包含行号信息，便于调试定位
3. **多语言支持**: 提供中文错误描述，提升用户体验
4. **组合机制**: 支持基础码+扩展码的组合模式
5. **向后兼容**: 保持错误码定义的向后兼容性

---
*文档生成时间: 2025-07-22*  
*基于工程: EPM_main*  
*文档版本: 2.0*  
*错误码总数: 500+*
