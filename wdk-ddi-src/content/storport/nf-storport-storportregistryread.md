---
UID: NF:storport.StorPortRegistryRead
title: StorPortRegistryRead function (storport.h)
description: The StorPortRegistryRead routine reads the registry data for the indicated device and value.
old-location: storage\storportregistryread.htm
tech.root: storage
ms.date: 08/12/2021
keywords: ["StorPortRegistryRead function"]
ms.keywords: StorPortRegistryRead, StorPortRegistryRead routine [Storage Devices], storage.storportregistryread, storport/StorPortRegistryRead, storprt_6eafcbbc-b767-45b3-97d6-86e591a29a19.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortRegistryRead
 - storport/StorPortRegistryRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortRegistryRead
---

# StorPortRegistryRead function

## -description

The **StorPortRegistryRead** routine reads the registry data for the indicated device and value.

## -parameters

### -param HwDeviceExtension

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls [**StorPortInitialize**](nf-storport-storportinitialize.md). The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.

### -param ValueName

Pointer to a UCHAR that specifies the registry value name whose content is to be read.

### -param Global

Indicates, when nonzero, that the port driver reads the contents of the registry value specified by **ValueName** under the Parameters\Device subkey. The values under the Device key apply to all adapters in the system. When **Global** is zero, the port driver reads the contents of the registry value specified by **ValueName** under the Parameters\Device(d) subkey, where (d) is a decimal value that corresponds to the port number of a particular adapter. In this case, the data retrieved is adapter-specific.

### -param Type

Indicates the data type of registry value. This parameter must have one of the values in the following table.

| Registry value data type | Meaning |
| ------------------------ | ------- |
| REG_NONE                       | No data type specified. |
| REG_SZ                         | Indicates a **NULL**-terminated Unicode string. |
| REG_EXPAND_SZ                  | Indicates a **NULL**-terminated Unicode string that includes environment variables that must be expanded to obtain the complete string. For example, a path name might be stored as the following string: "%USERPROFILE%\Application Data ". In this example, the environment variable USERPROFILE must be expanded to obtain the actual pathname. |
| REG_BINARY                     | Indicates a raw binary data. |
| REG_DWORD                      | Indicates a 32-bit double word value. |
| REG_DWORD_LITTLE_ENDIAN        | Indicates a 32-bit double word value, in little-endian order. This is identical to REG_DWORD. |
| REG_DWORD_BIG_ENDIAN           | Indicates a 32-bit double word value, in big-endian order. |
| REG_LINK                       | Indicates a Unicode string containing a symbolic link. |
| REG_MULTI_SZ                   | Indicates a series of **NULL**-terminated strings. |
| REG_RESOURCE_LIST              | Indicates that the registry value contains a list of hardware resources, also known as the "hardware resource map", that is stored under the HKEY_LOCAL_MACHINE\HARDWARE\ResourceMap hive. |
| REG_FULL_RESOURCE_DESCRIPTOR   | Indicates that the registry value contains a description of hardware resources stored under the HKEY_LOCAL_MACHINE\HARDWARE\Description hive. |
| REG_RESOURCE_REQUIREMENTS_LIST | Indicates that the registry value contains a list of hardware resource requirements stored under the HKEY_LOCAL_MACHINE\HARDWARE\ResourceMap tree. |
| REG_QWORD                      | Indicates that the registry value contains a 64-bit number.   |
| REG_QWORD_LITTLE_ENDIAN        | Indicates that the registry value contains a 64-bit number. This is the same data type as REG_QWORD. |

### -param Buffer

Pointer to the buffer where the retrieved registry information is to be reported.

### -param BufferLength

Pointer to a ULONG that contains the size, in bytes, of the registry data returned.

## -returns

**StorPortRegistryRead** returns a Boolean value of **TRUE** if the data pointed to by **ValueName** is successfully converted into ASCII and copied into the buffer. This routine returns **FALSE** in the event of an error.

## -remarks

If **StorPortRegistryRead** returns **FALSE** with a nonzero value in the **BufferLength** parameter, the buffer that was passed was too small and the **BufferLength** parameter reflects the correct buffer size that should be used. If the routine returns **FALSE** with the **BufferLength** parameter set to zero, another error has occurred.

The buffer used in this routine is allocated by calling [**StorPortAllocateRegistryBuffer**](nf-storport-storportallocateregistrybuffer.md) and freed by calling [**StorPortFreeRegistryBuffer**](nf-storport-storportfreeregistrybuffer.md).

## -see-also

[**StorPortAllocateRegistryBuffer**](nf-storport-storportallocateregistrybuffer.md)

[**StorPortFreeRegistryBuffer**](nf-storport-storportfreeregistrybuffer.md)

[**StorPortInitialize**](nf-storport-storportinitialize.md)
