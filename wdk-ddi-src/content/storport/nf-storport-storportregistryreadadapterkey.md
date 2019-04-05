---
UID: NF:storport.StorPortRegistryReadAdapterKey
title: StorPortRegistryReadAdapterKey function (storport.h)
description: The StorPortRegistryReadAdapterKey routine is called by the miniport driver to read the hardware or device registry adapter keys located in registry at HKLM/CurrentControlSet/Enum/&lt;Instance path&gt;/DeviceParameters/...
old-location: storage\storportregistryreadadapterkey.htm
tech.root: storage
ms.assetid: 85D43276-53A1-4CEE-99FE-23ED8BECB316
ms.date: 03/29/2018
ms.keywords: StorPortRegistryReadAdapterKey, StorPortRegistryWriteAdapterKey, StorPortRegistryWriteAdapterKey routine [Storage Devices], storage.storportregistryreadadapterkey, storport/StorPortRegistryWriteAdapterKey
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortRegistryWriteAdapterKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortRegistryReadAdapterKey function


## -description


The <b>StorPortRegistryReadAdapterKey</b> routine is called by the miniport driver to read the hardware or device registry adapter keys located in registry at HKLM/CurrentControlSet/Enum/&lt;Instance path&gt;/DeviceParameters/... these keys are read from in the <a href="https://msdn.microsoft.com/417a4ab0-9723-4b3b-aa8c-342598874d61">INF DDInstall.HW Section</a>.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.


### -param SubKeyName [in, optional]

The miniport subkey.


### -param ValueName [in]

The name of the Value under the key.


### -param ValueType [in]

One of the following registry data types.

<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
REG_SZ

</td>
<td>
Unicode null-terminated string.

</td>
</tr>
<tr>
<td>
REG_EXPAND_SZ

</td>
<td>
Unicode null-terminated string with environment variable references.

</td>
</tr>
<tr>
<td>
REG_BINARY

</td>
<td>
Binary data.

</td>
</tr>
<tr>
<td>
REG_DWORD

</td>
<td>
32-bit double word.

</td>
</tr>
<tr>
<td>
REG_DWORD_LITTLE_ENDIAN

</td>
<td>
32-bit double word with a little-endian format.

</td>
</tr>
<tr>
<td>
REG_DWORD_BIG_ENDIAN

</td>
<td>
32-bit double word with a big-endian format.

</td>
</tr>
<tr>
<td>
REG_LINK

</td>
<td>
Unicode string that specifies a symbolic link.

</td>
</tr>
<tr>
<td>
REG_MULTI_SZ

</td>
<td>
Multiple Unicode strings.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_LIST

</td>
<td>
Resource list in the resource map.

</td>
</tr>
<tr>
<td>
REG_FULL_RESOURCE_DESCRIPTOR

</td>
<td>
Resource list in the hardware description.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_REQUIREMENTS_LIST

</td>
<td>
Resource requirement list.

</td>
</tr>
<tr>
<td>
REG_QWORD

</td>
<td>
64-bit quadlet number.

</td>
</tr>
<tr>
<td>
REG_QWORD_LITTLE_ENDIAN

</td>
<td>
64-bit quadlet number with a little-endian format.

</td>
</tr>
</table>
 


### -param ValueData [in, out]

Pointer to a the data that contains the registry data to be read. The data is converted from UNICODE to a NULL-terminated ASCII string.


### -param ValueDataLength [in, out]

Specifies the size of the data pointed to by <i>ValueData</i>.


## -returns




            Returns STOR_STATUS_SUCCESS when the operation is successful, otherwise the appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>
 

 

