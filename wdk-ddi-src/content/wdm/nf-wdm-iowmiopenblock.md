---
UID: NF:wdm.IoWMIOpenBlock
title: IoWMIOpenBlock function
author: windows-driver-content
description: The IoWMIOpenBlock routine opens the WMI data block object for the specified WMI class.
old-location: kernel\iowmiopenblock.htm
old-project: kernel
ms.assetid: c23d1861-59df-4bd4-a005-173ccac53049
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/IoWMIOpenBlock, k104_19f378c4-3729-4668-aef0-0e675d2e1ae4.xml, IoWMIOpenBlock, IoWMIOpenBlock routine [Kernel-Mode Driver Architecture], kernel.iowmiopenblock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Ntifs.h. The WMIGUID_XXX values are declared in Wmistr.h. To use them, include Wmistr.h.
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
-	IoWMIOpenBlock
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIOpenBlock function


## -description


The <b>IoWMIOpenBlock</b> routine opens the WMI data block object for the specified WMI class.


## -syntax


````
NTSTATUS IoWMIOpenBlock(
  _In_  GUID  *DataBlockGuid,
  _In_  ULONG DesiredAccess,
  _Out_ PVOID *DataBlockObject
);
````


## -parameters




### -param Guid

TBD


### -param DesiredAccess [in]

Specifies the desired access rights to the data block object. The caller must have particular access rights to perform certain operations. 

The following is a description of each access right bit and the operations it allows:





#### WMIGUID_EXECUTE

The data block object can be used to run WMI class methods. This flag must be set to use <a href="..\wdm\nf-wdm-iowmiexecutemethod.md">IoWMIExecuteMethod</a> on the data block object. 



#### WMIGUID_NOTIFICATION

The data block object can be used to register event notification callbacks. This flag must be set to use <a href="..\wdm\nf-wdm-iowmisetnotificationcallback.md">IoWMISetNotificationCallback</a>, and can only be used for WMI event blocks. Callers that specify this flag must also specify the SYNCHRONIZE flag.



#### WMIGUID_QUERY

The data block object can be used to query WMI class properties. This flag must be set to use any of the <b>IoWMIQuery<i>Xxx</i></b> routines on the data block object. 



#### WMIGUID_SET

The data block object can be used to set WMI class properties. This flag must be set to use any of the <b>IoWMISet<i>Xxx</i></b> routines on the data block object. 


### -param DataBlockObject [out]

Pointer to a memory location where the routine returns a pointer to the data block object.


#### - DataBlockGuid [in]

Specifies the GUID for WMI class.


## -returns



Returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



The caller uses <b>IoWMIOpenBlock</b> to create a data block object for the specified WMI class GUID. Subsequently, the caller can use the data block object to read or write WMI class properties, run WMI class methods, and register callbacks for WMI events.

Use the <b>IoWMIQuery<i>Xxx</i></b> and <b>IoWMISet<i>Xxx</i></b> routines to read and write WMI class properties. Use <a href="..\wdm\nf-wdm-iowmiexecutemethod.md">IoWMIExecuteMethod</a> to run WMI class methods, and use <a href="..\wdm\nf-wdm-iowmisetnotificationcallback.md">IoWMISetNotificationCallback</a> to register a WMI event notification callback.

Use <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> to close the data block object once it is no longer needed.




## -see-also

<a href="..\wdm\nf-wdm-iowmisetsingleinstance.md">IoWMISetSingleInstance</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-iowmiqueryalldata.md">IoWMIQueryAllData</a>



<a href="..\wdm\nf-wdm-iowmiexecutemethod.md">IoWMIExecuteMethod</a>



<a href="..\wdm\nf-wdm-iowmiquerysingleinstancemultiple.md">IoWMIQuerySingleInstanceMultiple</a>



<a href="..\wdm\nf-wdm-iowmiqueryalldatamultiple.md">IoWMIQueryAllDataMultiple</a>



<a href="..\wdm\nf-wdm-iowmiquerysingleinstance.md">IoWMIQuerySingleInstance</a>



<a href="..\wdm\nf-wdm-iowmisetsingleitem.md">IoWMISetSingleItem</a>



<a href="..\wdm\nf-wdm-iowmisetnotificationcallback.md">IoWMISetNotificationCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIOpenBlock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

