---
UID: NC:hdaudio.PTRANSFER_CODEC_VERBS
title: PTRANSFER_CODEC_VERBS
author: windows-driver-content
description: The TransferCodecVerbs routine transfers one or more commands to a codec or codecs and retrieves the responses to those commands.The function pointer type for a TransferCodecVerbs routine is defined as follows.
old-location: audio\transfercodecverbs.htm
tech.root: audio
ms.assetid: 0ba92f5c-c4a3-48de-b8af-9c444b2e65b5
ms.date: 5/8/2018
ms.keywords: PTRANSFER_CODEC_VERBS, PTRANSFER_CODEC_VERBS callback, TransferCodecVerbs, TransferCodecVerbs callback function [Audio Devices], aud-prop2_120467b8-2871-49f5-9e5a-0715505e786e.xml, audio.transfercodecverbs, hdaudio/TransferCodecVerbs
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	TransferCodecVerbs
product:
- Windows
targetos: Windows
req.typenames: 
---

# PTRANSFER_CODEC_VERBS callback function


## -description


The <i>TransferCodecVerbs</i> routine transfers one or more commands to a codec or codecs and retrieves the responses to those commands.

The function pointer type for a <i>TransferCodecVerbs</i> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="https://msdn.microsoft.com/library/windows/hardware/ff536418">HDAUDIO_BUS_INTERFACE_V2</a><u>,</u> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Count [in]

Specifies the number of elements in the <i>codecTransfer</i> array.


### -param CodecTransfer [in, out]

Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff536424">HDAUDIO_CODEC_TRANSFER</a> structures. Each array element is a structure that contains storage for both an output command from the caller and the corresponding input response from the codec.


### -param Callback [in]

Function pointer to a callback routine. This parameter is a function pointer of type HDAUDIO_TRANSFER_COMPLETE_CALLBACK. The parameter can be specified as <b>NULL</b>. For more information, see the following Remarks section.


### -param Context








#### - CallbackContext [in]

A context value for the callback routine. The caller casts the context value to type PVOID. After completing the commands asynchronously, the HD Audio bus driver passes the context value to the callback routine as a call parameter.


## -returns



<i>TransferCodecVerbs</i> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the request could not be added to the command queue due to a shortage of nonpaged memory.

</td>
</tr>
</table>
 




## -remarks



This routine submits one or more codec commands to the HD Audio bus driver. The bus driver issues the commands to the codecs, retrieves the codecs' responses to the commands, and outputs the responses to the caller.

The caller specifies the commands in an array of HDAUDIO_CODEC_TRANSFER structures. Each structure contains storage for both a command and the codec's response to that command. Before calling <i>TransferCodecVerbs</i>, the caller fills in the commands in each of the structures in the array. As each command completes, the HD Audio bus driver retrieves the codec's response and writes it into the structure. After the last command completes, the caller can read the responses from the array.

The routine can operate either synchronously or asynchronously:

<ul>
<li>
If the caller specifies <b>NULL</b> for the value of input parameter <i>callback</i>, the HD Audio bus driver completes the commands in the <i>codecTransfer</i> array synchronously. (In other words, the routine returns only after the codecs have processed all the commands and the responses to those commands are available.)

</li>
<li>
If the caller specifies a non-<b>NULL</b> value for the <i>callback</i> parameter, the routine operates asynchronously. (In other words, the routine returns immediately after adding the commands to its internal queue without waiting for the codecs to process all the commands.) After the codecs process the commands, the HD Audio bus driver calls the callback routine. In the asynchronous case, the caller should not attempt to read the responses to the commands before the bus driver calls the callback routine.

</li>
</ul>
The function pointer type for the callback parameter is defined as:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
  (*PHDAUDIO_TRANSFER_COMPLETE_CALLBACK)
    (HDAUDIO_CODEC_TRANSFER *, PVOID);</pre>
</td>
</tr>
</table></span></div>
The first call parameter is a pointer to the <i>codecTransfer</i> array element that contains the codec command and the response that triggered the callback. The second call parameter is the same context value that was specified previously in the <i>TransferCodecVerbs</i> routine's <i>callbackContext</i> parameter.

If successful, <i>TransferCodecVerbs</i> returns STATUS_SUCCESS. The meaning of this status code depends on whether the routine operates synchronously or asynchronously:

<ul>
<li>
In the synchronous case (<i>callback</i> is <b>NULL</b>), STATUS_SUCCESS means that the bus driver has all the commands in the codecTransfer array to the codecs and that the routine has written all the responses to those commands into the array. However, the caller must check the individual responses to determine whether they are valid. Individual responses might be invalid due to codec timeouts or FIFO overrun.

</li>
<li>
In the asynchronous case (<i>callback</i> is non-<b>NULL</b>), STATUS_SUCCESS means only that the routine has successfully added the commands to the HD Audio bus driver's internal queue. The caller must not attempt to read the responses to those commands until the bus driver calls the callback routine.

</li>
</ul>
If a response is invalid due to a FIFO overrun, the likely cause is that the codec responded to the command but the response was lost due to an insufficiently sized response input ring buffer (RIRB). If a FIFO overrun is not the cause of the invalid response, the failure probably occurred because the codec did not respond in time (timed out). In this case, the caller can assume that the command did not reach the codec.

If the <i>callback</i> parameter is <b>NULL</b>, the caller must be running at IRQL PASSIVE_LEVEL. If <i>callback</i> is non-<b>NULL</b>, the caller can call <i>TransferCodecVerbs</i> at IRQL &lt;= DISPATCH_LEVEL, in which case the call returns immediately without waiting for the codecs to process all the commands; after the commands complete, the HD Audio bus driver calls the callback routine at IRQL DISPATCH_LEVEL.

The caller must allocate the <i>codecTransfer</i> array from the nonpaged pool.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536418">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536424">HDAUDIO_CODEC_TRANSFER</a>
 

 

