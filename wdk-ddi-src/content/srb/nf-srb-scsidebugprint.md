---
UID: NF:srb.ScsiDebugPrint
title: ScsiDebugPrint function
author: windows-driver-content
description: The ScsiDebugPrint routine prints debug information with a level of verbosity based on global values set in the kernel debugger or set in the registry and initialized when the system boots.
old-location: storage\scsidebugprint.htm
old-project: storage
ms.assetid: bbf3ea14-1802-4433-9043-73bfc0c447bf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiDebugPrint routine [Storage Devices], scsiprt_ef011e55-85be-4ec8-8ba3-3838417bcd15.xml, srb/ScsiDebugPrint, ScsiDebugPrint, storage.scsidebugprint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Scsiport.lib
-	Scsiport.dll
apiname:
-	ScsiDebugPrint
product: Windows
targetos: Windows
req.typenames: "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product: Windows 10 or later.
---

# ScsiDebugPrint function


## -description


The <b>ScsiDebugPrint</b> routine prints debug information with a level of verbosity based on global values set in the kernel debugger or set in the registry and initialized when the system boots. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID ScsiDebugPrint(
   ULONG  DebugPrintLevel,
   PCCHAR DebugMessage
);
````


## -parameters




### -param DebugPrintLevel

Contains a value between 0 and 3 that specifies the amount of verbosity. A value of 3 signifies the highest level of verbosity. A value of 0 signifies the lowest level. <b>ScsiDebugPrint</b> will print the message pointed to by <i>DebugMessage</i>, together with other debugging information. For information about how the meaning of <i>DebugPrintLevel </i>has changed in Windows XP and later operating systems, see the remarks section.  


### -param DebugMessage

Pointer to the message to be printed. 


### -param param

TBD



## -returns


None



## -remarks


Prior to Windows XP, the <b>ScsiDebugPrint</b> routine compared the value passed to it in the <i>DebugPrintLevel </i>parameter with the value of the global variable <i>ScsiDebug</i>.and printed the <i>DebugMessage </i>string and diagnostic output whenever <i>DebugPrintLevel</i> was less than or equal to <i>ScsiDebug</i>. If <i>DebugPrintLevel</i> was <i>greater</i> than <i>ScsiDebug</i>.<b>ScsiDebugPrint</b> did not print anything. 

In Windows XP and later operating systems, <b>ScsiDebugPrint</b> no longer compares <i>DebugPrintLevel </i>to <i>ScsiDebug. </i>Instead, <b>ScsiDebugPrint</b> simply calls the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff543634">DbgPrintEx</a> and passes it the <i>DebugMessage </i>pointer. Before <b>ScsiDebugPrint</b> calls <b>DbgPrintEx</b> it maps the value passed in <i>DebugPrintLevel </i>to a value used by <b>DbgPrintEx</b> as follows. 
<table>
<tr>
<th>Value in <i>DebugPrintLevel</i></th>
<th>Value Passed to DbgPrintEx</th>
</tr>
<tr>
<td>
0

</td>
<td>
DPFLTR_WARNING_LEVEL

</td>
</tr>
<tr>
<td>
1

</td>
<td>
DPFLTR_TRACE_LEVEL

</td>
</tr>
<tr>
<td>
2

</td>
<td>
DPFLTR_TRACE_LEVEL

</td>
</tr>
<tr>
<td>
3

</td>
<td>
DPFLTR_INFO_LEVEL

</td>
</tr>
</table> 

To view the message pointed to by <i>DebugMessage </i>from the kernel debugger, use the component filter mask Kd_ScsiMiniPort_Mask. For more information about debugging masks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543634">DbgPrintEx</a>. 

<b>ScsiDebugPrint</b> only functions in checked builds. <b>ScsiDebugPrint</b> compiles to nothing in free builds. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543634">DbgPrintEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiDebugPrint routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

