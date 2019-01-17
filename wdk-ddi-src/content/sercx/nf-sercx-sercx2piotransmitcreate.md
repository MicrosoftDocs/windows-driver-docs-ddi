---
UID: NF:sercx.SerCx2PioTransmitCreate
title: SerCx2PioTransmitCreate function
description: The SerCx2PioTransmitCreate method creates a PIO-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform PIO-transmit transactions.
old-location: serports\sercx2piotransmitcreate.htm
tech.root: serports
ms.assetid: 550A26D0-18A5-47F9-B769-B76FA2EB1734
ms.date: 04/23/2018
ms.keywords: 2/SerCx2PioTransmitCreate, SerCx2PioTransmitCreate, SerCx2PioTransmitCreate method [Serial Ports], serports.sercx2piotransmitcreate
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	2.0\Sercx.h
api_name:
-	SerCx2PioTransmitCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2PioTransmitCreate function


## -description


The <b>SerCx2PioTransmitCreate</b> method creates a PIO-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform PIO-transmit transactions.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>.


### -param PioTransmitConfig [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a> structure. Before calling this method, the caller must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265335">SERCX2_PIO_TRANSMIT_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform PIO-transmit transactions.


### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new PIO-transmit object. Before calling this method, the caller must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param PioTransmit [out]

A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to the newly created PIO-transmit object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## -returns



This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
A PIO-transmit object already exists from a previous <b>SerCx2PioTransmitCreate</b> call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>Config</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_PIO_TRANSMIT_CONFIG</b>).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified combination of implemented callback functions is not valid. The driver must implement the <a href="https://msdn.microsoft.com/28DD175B-9869-4CFC-9BDD-172DA7E015DE">EvtSerCx2PioTransmitWriteBuffer</a>, <a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a>, and <a href="https://msdn.microsoft.com/2483F6A6-67FE-4C75-9872-53F66B4BD658">EvtSerCx2PioTransmitCancelReadyNotification</a> functions. The driver must implement either all three or none of the <a href="https://msdn.microsoft.com/A21E14DA-0B76-4DA2-B628-C3A4DE843FA9">EvtSerCx2PioTransmitDrainFifo</a>, <a href="https://msdn.microsoft.com/DAAE9C91-F83F-4D14-8851-7B5DEEA340B3">EvtSerCx2PioTransmitCancelDrainFifo</a>, and <a href="https://msdn.microsoft.com/2BB02F84-01C1-432D-A4A9-6035F3ED32D7">EvtSerCx2PioTransmitPurgeFifo</a> functions.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to perform the requested operation.

</td>
</tr>
</table>
 




## -remarks



Your serial controller driver calls this method to create a PIO-transmit object. SerCx2 uses this object to perform PIO-transmit transactions, which are transactions that use programmed I/O (PIO) to write data to the serial controller to be transmitted.

Typically, a serial controller driver calls <b>SerCx2PioTransmitCreate</b> from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> function. The driver must call this method only after it successfully calls the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a> method.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the PIO-transmit object, and to supply pointers to <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> and <a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating PIO-transmit objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>. For more information about PIO-transmit operations, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.




## -see-also




<a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a>



<a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a>



<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265335">SERCX2_PIO_TRANSMIT_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>
 

 

