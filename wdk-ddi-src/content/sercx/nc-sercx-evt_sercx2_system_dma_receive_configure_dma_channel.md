---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL
title: EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL (sercx.h)
description: The EvtSerCx2SystemDmaReceiveConfigureDmaChannel event callback function is called by version 2 of the serial framework extension (SerCx2) to let the serial controller driver do any custom configuration of the DMA adapter that might be required before the start of each transfer in a system-DMA-receive transaction.
old-location: serports\evtsercx2systemdmareceiveconfiguredmachannel.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaReceiveConfigureDmaChannel, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL callback, EvtSerCx2SystemDmaReceiveConfigureDmaChannel, EvtSerCx2SystemDmaReceiveConfigureDmaChannel callback function [Serial Ports], serports.evtsercx2systemdmareceiveconfiguredmachannel
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL
 - sercx/EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL
---

# EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL callback function


## -description

The <i>EvtSerCx2SystemDmaReceiveConfigureDmaChannel</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to let the serial controller driver do any custom configuration of the DMA adapter that might be required before the start of each transfer in a system-DMA-receive transaction.

## -parameters

### -param SystemDmaReceive 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method to create this object.

### -param Mdl 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> that describes the memory pages that are spanned by the read buffer for the system-DMA-receive transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.

### -param Offset 

[in]
The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.

### -param Length 

[in]
The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.

## -returns

The <i>EvtSerCx2SystemDmaReceiveConfigureDmaChannel</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## -remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object.

Before initiating a system-DMA-receive transaction, SerCx2 calls the <i>EvtSerCx2SystemDmaReceiveConfigureDmaChannel</i> function, if it is implemented. This function performs any special configuration of the system DMA controller that might be required before SerCx2 starts the system-DMA-receive transaction.

The serial controller driver can call a method such as <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivegetdmaenabler">SerCx2SystemDmaReceiveGetDmaEnabler</a> to get the DMA enabler for the system DMA controller used for system-DMA-receive transactions.

For more information, see <a href="/previous-versions/dn265343(v=vs.85)">SerCx2 System-DMA-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaReceiveConfigureDmaChannel</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaReceiveConfigureDmaChannel</i> callback function that is named <code>MySystemDmaReceiveConfigureDmaChannel</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL  MySystemDmaReceiveConfigureDmaChannel;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
NTSTATUS
  MySystemDmaReceiveConfigureDmaChannel(
    SERCX2SYSTEMDMARECEIVE SystemDmaReceive,
    PMDL Mdl,
    ULONG Offset,
    ULONG Length
    )
  {...}
```

The <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CONFIGURE_DMA_CHANNEL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivegetdmaenabler">SerCx2SystemDmaReceiveGetDmaEnabler</a>

