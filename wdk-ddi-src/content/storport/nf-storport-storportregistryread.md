---
UID: NF:storport.StorPortRegistryRead
title: StorPortRegistryRead function
description: The StorPortRegistryRead routine reads the registry data for the indicated device and value.
old-location: storage\storportregistryread.htm
tech.root: storage
ms.assetid: 16f13973-c1c1-4123-8fa4-20187ec2c204
ms.date: 03/29/2018
ms.keywords: StorPortRegistryRead, StorPortRegistryRead routine [Storage Devices], storage.storportregistryread, storport/StorPortRegistryRead, storprt_6eafcbbc-b767-45b3-97d6-86e591a29a19.xml
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortRegistryRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortRegistryRead function


## -description


The <b>StorPortRegistryRead</b> routine reads the registry data for the indicated device and value. 


## -parameters




### -param HwDeviceExtension

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.


### -param ValueName

Pointer to a UCHAR that specifies the registry value name whose content is to be read. 


### -param Global

Indicates, when nonzero, that the port driver reads the contents of the registry value specified by <i>ValueName</i> under the Parameters\Device subkey. The values under the Device key apply to all adapters in the system. When <i>Global</i> is zero, the port driver reads the contents of the registry value specified by <i>ValueName</i> under the Parameters\Device(d) subkey, where (d) is a decimal value that corresponds to the port number of a particular adapter. In this case, the data retrieved is adapter-specific. 


### -param Type

Indicates the data type of registry value. This parameter must have one of the values in the following table.

<table>
<tr>
<th>Registry value data type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
REG_NONE

</td>
<td>
No data type specified. 

</td>
</tr>
<tr>
<td>
REG_SZ

</td>
<td>
Indicates a <b>NULL</b>-terminated Unicode string.

</td>
</tr>
<tr>
<td>
REG_EXPAND_SZ

</td>
<td>
Indicates a <b>NULL</b>-terminated Unicode string that includes environment variables that must be expanded to obtain the complete string. For example, a path name might be stored as the following string: "%USERPROFILE%\Application Data ".

In this example, the environment variable USERPROFILE must be expanded to obtain the actual pathname.

</td>
</tr>
<tr>
<td>
REG_BINARY

</td>
<td>
Indicates a raw binary data.

</td>
</tr>
<tr>
<td>
REG_DWORD

</td>
<td>
Indicates a 32-bit double word value.

</td>
</tr>
<tr>
<td>
REG_DWORD_LITTLE_ENDIAN

</td>
<td>
Indicates a 32-bit double word value, in little-endian order. This is identical to REG_DWORD.

</td>
</tr>
<tr>
<td>
REG_DWORD_BIG_ENDIAN

</td>
<td>
Indicates a 32-bit double word value, in big-endian order. 

</td>
</tr>
<tr>
<td>
REG_LINK

</td>
<td>
Indicates a Unicode string containing a symbolic link. 

</td>
</tr>
<tr>
<td>
REG_MULTI_SZ

</td>
<td>
Indicates a series of <b>NULL</b>-terminated strings.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_LIST

</td>
<td>
Indicates that the registry value contains a list of hardware resources, also known as the "hardware resource map", that is stored under the HKEY_LOCAL_MACHINE\HARDWARE\ResourceMap hive.

</td>
</tr>
<tr>
<td>
REG_FULL_RESOURCE_DESCRIPTOR

</td>
<td>
Indicates that the registry value contains a description of hardware resources stored under the HKEY_LOCAL_MACHINE\HARDWARE\Description hive.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_REQUIREMENTS_LIST

</td>
<td>
Indicates that the registry value contains a list of hardware resource requirements stored under the HKEY_LOCAL_MACHINE\HARDWARE\ResourceMap tree.

</td>
</tr>
<tr>
<td>
REG_QWORD

</td>
<td>
Indicates that the registry value contains a 64-bit number.

</td>
</tr>
<tr>
<td>
REG_QWORD_LITTLE_ENDIAN

</td>
<td>
Indicates that the registry value contains a 64-bit number. This is the same data type as REG_QWORD. 

</td>
</tr>
</table>
 


### -param Buffer

Pointer to the buffer where the retrieved registry information is to be reported. 


### -param BufferLength

Pointer to a ULONG that contains the size, in bytes, of the registry data returned. 


## -returns



<b>StorPortRegistryRead</b> returns a Boolean value of <b>TRUE</b> if the data pointed to by <i>ValueName</i> is successfully converted into ASCII and copied into the buffer. This routine returns <b>FALSE</b> in the event of an error. 




## -remarks



If <b>StorPortRegistryRead</b> returns <b>FALSE</b> with a nonzero value in the <i>BufferLength</i> parameter, the buffer that was passed was too small and the <i>BufferLength</i> parameter reflects the correct buffer size that should be used. If the routine returns <b>FALSE</b> with the <i>BufferLength</i> parameter set to zero, another error has occurred.

The buffer used in this routine is allocated by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567034">StorPortAllocateRegistryBuffer</a> and freed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567067">StorPortFreeRegistryBuffer</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567034">StorPortAllocateRegistryBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567067">StorPortFreeRegistryBuffer</a>
 

 

