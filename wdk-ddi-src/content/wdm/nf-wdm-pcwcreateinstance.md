---
UID: NF:wdm.PcwCreateInstance
title: PcwCreateInstance function
author: windows-driver-content
description: The PcwCreateInstance function creates a new instance for the specified registered counter set.
old-location: devtest\pcwcreateinstance.htm
old-project: devtest
ms.assetid: ed9bd8fa-a6e6-465a-8415-3e9c19233419
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PcwCreateInstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcwCreateInstance
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PcwCreateInstance function



## -description
The <b>PcwCreateInstance</b> function creates a new instance for the specified registered counter set.



## -syntax

````
NTSTATUS PcwCreateInstance(
  _Out_ PPCW_INSTANCE     *Instance,
  _In_  PPCW_REGISTRATION Registration,
  _In_  PCUNICODE_STRING  Name,
  _In_  ULONG             Count,
  _In_  PPCW_DATA         Data
);
````


## -parameters

### -param Instance [out]

A pointer to receive the newly created instance.


### -param Registration [in]

A pointer to the registered provider that owns this instance of the counter set.


### -param Name [in]

A pointer to the Unicode string that contains the name of the instance of the counter set.


### -param Count [in]

The number of data blocks that are associated with this instance.


### -param Data [in]

A pointer to an array of data blocks that contains the counter values of this instance.


## -returns
This function returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The instance was successfully created,
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>The number of structures, specified by <i>Count</i>, is not valid for the registered provider.
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>A problem was detected with the size of the data buffer and the counter set,
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>The size of the structure, specified by <i>Count</i>, overflows the data buffer,

 


## -remarks
Before the provider uses this function, the provider must call the <a href="..\wdm\nf-wdm-pcwregister.md">PcwRegister</a> function to create a registration.

Use the <a href="..\wdm\nf-wdm-pcwcloseinstance.md">PcwCloseInstance</a> function to close this instance.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-pcwcloseinstance.md">PcwCloseInstance</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pcwregister.md">PcwRegister</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PcwCreateInstance function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

