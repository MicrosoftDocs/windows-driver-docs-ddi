---
UID: NF:storport.StorPortRegistryWriteAdapterKey
title: StorPortRegistryWriteAdapterKey function
author: windows-driver-content
description: The StorPortRegistryWriteAdapterKey routine is called by the miniport driver to write the hardware or device registry adapter keys located in registry at HKLM/CurrentControlSet/Enum/&lt;Instance path&gt;/DeviceParameters/...
old-location: storage\storportregistrywriteadapterkey.htm
old-project: storage
ms.assetid: D995FB36-177A-44BF-9326-EB2820DB0962
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortRegistryWriteAdapterKey, storage.storportregistrywriteadapterkey, StorPortRegistryWriteAdapterKey routine [Storage Devices], StorPortRegistryWriteAdapterKey
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortRegistryWriteAdapterKey
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortRegistryWriteAdapterKey function


## -description


The <b>StorPortRegistryWriteAdapterKey</b> routine is called by the miniport driver to write the hardware or device registry adapter keys located in registry at HKLM/CurrentControlSet/Enum/&lt;Instance path&gt;/DeviceParameters/... these keys are written at in the <a href="https://msdn.microsoft.com/417a4ab0-9723-4b3b-aa8c-342598874d61">INF DDInstall.HW Section</a>.


## -syntax


````
STORPORT_STATUS StorPortRegistryWriteAdapterKey(
  _In_     PVOID  HwDeviceExtension,
  _In_opt_ PCWSTR SubKeyName,
  _In_     PCWSTR ValueName,
  _In_     ULONG  ValueType,
  _In_     PVOID  ValueData,
  _In_     ULONG  ValueDataLength
);
````


## -parameters




#### - HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.


#### - SubKeyName [in, optional]

The miniport subkey.


#### - ValueName [in]

The name of the Value under the key.


#### - ValueType [in]

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


#### - ValueData [in]

Pointer to a the data that contains the registry data to be written. The data is converted from UNICODE to a NULL-terminated ASCII string.


#### - ValueDataLength [in]

Specifies the size of the data pointed to by <i>ValueData</i>.


## -returns



            Returns STOR_STATUS_SUCCESS when the operation is successful, otherwise the appropriate error code.



## -see-also

<a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortRegistryWriteAdapterKey routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

