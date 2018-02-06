---
UID: NF:wdm.IoWMIHandleToInstanceName
title: IoWMIHandleToInstanceName function
author: windows-driver-content
description: The IoWMIHandleToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a file handle.
old-location: kernel\iowmihandletoinstancename.htm
old-project: kernel
ms.assetid: e9d8fde5-81b7-480b-8d7c-0005fd1868fb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IoWMIHandleToInstanceName, IoWMIHandleToInstanceName, kernel.iowmihandletoinstancename, IoWMIHandleToInstanceName routine [Kernel-Mode Driver Architecture], k104_7d97f756-2f7f-4788-bcbc-368e08b6b86f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoWMIHandleToInstanceName
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIHandleToInstanceName function


## -description


The <b>IoWMIHandleToInstanceName</b> routine determines the instance name for the WMI class instance implemented by the driver that is specified by a file handle.


## -syntax


````
NTSTATUS IoWMIHandleToInstanceName(
  _In_  PVOID           DataBlockObject,
  _In_  HANDLE          FileHandle,
  _Out_ PUNICODE_STRING InstanceName
);
````


## -parameters




### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. 


### -param FileHandle [in]

Specifies a file handle. The routine returns the instance name corresponding to the driver that is represented by the file handle. 


### -param InstanceName [out]

Pointer to the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that the routine uses to return the instance name. The caller frees the returned buffer within <b>UNICODE_STRING</b>. 


## -returns


The routine returns an NTSTATUS code. Possible return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded. The routine fills the <b>UNICODE_STRING</b> structure pointed to by the <i>InstanceName</i> parameter with the instance name.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The driver does not implement any instances of the WMI class specified by <i>DataBlockObject</i>.

</td>
</tr>
</table> 



## -see-also

<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>

<a href="..\wdm\nf-wdm-iowmideviceobjecttoinstancename.md">IoWMIDeviceObjectToInstanceName</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIHandleToInstanceName routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

