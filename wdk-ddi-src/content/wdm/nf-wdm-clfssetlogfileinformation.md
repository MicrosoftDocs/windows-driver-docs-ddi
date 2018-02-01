---
UID: NF:wdm.ClfsSetLogFileInformation
title: ClfsSetLogFileInformation function
author: windows-driver-content
description: The ClfsSetLogFileInformation routine sets metadata and state information for a specified stream and its underlying physical log.
old-location: kernel\clfssetlogfileinformation.htm
old-project: kernel
ms.assetid: 9f44b1ce-25d4-438f-b4eb-cff7bbfb5e0a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsSetLogFileInformation, ClfsSetLogFileInformation routine [Kernel-Mode Driver Architecture], kernel.clfssetlogfileinformation, Clfs_15ad655b-ee70-4ee8-9868-4e7ab96dfb3a.xml, wdm/ClfsSetLogFileInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsSetLogFileInformation
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsSetLogFileInformation function


## -description


The <b>ClfsSetLogFileInformation</b> routine sets metadata and state information for a specified stream and its underlying physical log.


## -syntax


````
NTSTATUS ClfsSetLogFileInformation(
  _In_ PLOG_FILE_OBJECT           plfoLog,
  _In_ CLFS_LOG_INFORMATION_CLASS eInformationClass,
  _In_ PVOID                      pinfoBuffer,
  _In_ ULONG                      cbBuffer
);
````


## -parameters




### -param plfoLog [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.


### -param eInformationClass [in]

A <a href="..\wdm\ne-wdm-_cls_log_information_class.md">CLFS_LOG_INFORMATION_CLASS</a> value that specifies the class of information being set.


### -param pinfoBuffer [in]

A pointer to a buffer that supplies the log information. The structure of this buffer varies according to the class of information specified by <i>eInformationClass</i>. The following table shows the relationship between the information class and the buffer type.
<table>
<tr>
<th>Value of eInformationClass</th>
<th>Type of buffer pointed to by <i>pinfoBuffer</i></th>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_cls_information.md">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformationPhysical</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_cls_information.md">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogNameInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_clfs_log_name_information.md">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogPhysicalNameInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_clfs_log_name_information.md">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogStreamIdentifierInformation</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_clfs_stream_id_information.md">CLFS_STREAM_ID_INFORMATION</a>


</td>
</tr>
</table> 


### -param cbBuffer [in]

The size, in bytes, of the buffer pointed to by <i>pinfoBuffer</i>.


## -returns


<b>ClfsSetLogFileInformation</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.



## -see-also

<a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a>

<a href="..\wdm\nf-wdm-clfsquerylogfileinformation.md">ClfsQueryLogFileInformation</a>

<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>

<a href="..\wdm\ns-wdm-_cls_information.md">CLFS_INFORMATION</a>

<a href="..\wdm\ns-wdm-_clfs_stream_id_information.md">CLFS_STREAM_ID_INFORMATION</a>

<a href="..\wdm\ne-wdm-_cls_log_information_class.md">CLFS_LOG_INFORMATION_CLASS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsSetLogFileInformation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

