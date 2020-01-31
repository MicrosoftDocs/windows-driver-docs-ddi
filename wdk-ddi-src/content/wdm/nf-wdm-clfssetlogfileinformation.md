---
UID: NF:wdm.ClfsSetLogFileInformation
title: ClfsSetLogFileInformation function (wdm.h)
description: The ClfsSetLogFileInformation routine sets metadata and state information for a specified stream and its underlying physical log.
old-location: kernel\clfssetlogfileinformation.htm
tech.root: kernel
ms.assetid: 9f44b1ce-25d4-438f-b4eb-cff7bbfb5e0a
ms.date: 04/30/2018
ms.keywords: ClfsSetLogFileInformation, ClfsSetLogFileInformation routine [Kernel-Mode Driver Architecture], Clfs_15ad655b-ee70-4ee8-9868-4e7ab96dfb3a.xml, kernel.clfssetlogfileinformation, wdm/ClfsSetLogFileInformation
f1_keywords:
 - "wdm/ClfsSetLogFileInformation"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsSetLogFileInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsSetLogFileInformation function


## -description


The <b>ClfsSetLogFileInformation</b> routine sets metadata and state information for a specified stream and its underlying physical log.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param eInformationClass [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_cls_log_information_class">CLFS_LOG_INFORMATION_CLASS</a> value that specifies the class of information being set.


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_information">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformationPhysical</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_information">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogNameInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_log_name_information">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogPhysicalNameInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_log_name_information">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogStreamIdentifierInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_stream_id_information">CLFS_STREAM_ID_INFORMATION</a>


</td>
</tr>
</table>
 


### -param cbBuffer [in]

The size, in bytes, of the buffer pointed to by <i>pinfoBuffer</i>.


## -returns



<b>ClfsSetLogFileInformation</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_information">CLFS_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_cls_log_information_class">CLFS_LOG_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_stream_id_information">CLFS_STREAM_ID_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsquerylogfileinformation">ClfsQueryLogFileInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a>
 

 

