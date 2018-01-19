---
UID: NF:sercx.SerCx2CustomReceiveCreate
title: SerCx2CustomReceiveCreate function
author: windows-driver-content
description: The SerCx2CustomReceiveCreate method creates a custom-receive object, which version 2 of the serial framework extension (SerCx2) uses to read receive data from the serial controller by means of a custom data-transfer mechanism.
old-location: serports\sercx2customreceivecreate.htm
old-project: serports
ms.assetid: EC2DBC18-C3F6-4663-891E-AFF43A6D1CE3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2CustomReceiveCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCx2CustomReceiveCreate
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveCreate function



## -description
The <b>SerCx2CustomReceiveCreate</b> method creates a custom-receive object, which version 2 of the serial framework extension (SerCx2) uses to read receive data from the serial controller by means of a custom data-transfer mechanism.



## -syntax

````
NTSTATUS SerCx2CustomReceiveCreate(
  [in]  WDFDEVICE                     Device,
  [in]  PSERCX2_CUSTOM_RECEIVE_CONFIG CustomReceiveConfig,
  [in]  PWDF_OBJECT_ATTRIBUTES        Attributes,
  [out] SERCX2CUSTOMRECEIVE           *CustomReceive
);
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.


### -param CustomReceiveConfig [in]

A pointer to a <a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a> structure. Before calling this method, the caller must call the <a href="..\sercx\nf-sercx-sercx2_custom_receive_config_init.md">SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform custom-receive transactions.


### -param Attributes [in]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new custom-receive object. Before calling this method, the caller must call the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param CustomReceive [out]

A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a> handle to the newly created custom-receive object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## -returns
This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>A custom-receive object already exists from a previous <b>SerCx2CustomReceiveCreate</b> call; or a system-DMA-receive object exists from a previous <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2CustomReceiveCreate</a> call; or a system-DMA-transmit object exists from a previous <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2CustomTransmitCreate</a> call; or <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> has not yet been called to create a PIO-receive object.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A parameter value is not valid.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The <i>Config</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_CONFIG</b>).
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient resources are available to create the custom-receive object.

 


## -remarks
This method is called by the serial controller driver to create a custom-receive object. SerCx2 uses this object to do custom-receive transactions, which are transactions that use a custom data-transfer mechanism to read data received by the serial controller.

A serial controller driver must successfully call the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> and <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> methods before calling <b>SerCx2CustomReceiveCreate</b>.

Before calling <b>SerCx2CustomReceiveCreate</b>, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2_custom_receive_config_init.md">SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</a> function to initialize the <a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a> structure pointed to by <i>CustomReceiveConfig</i>. This function sets the following members of the structure to zero:

If necessary, the serial controller driver can set any of these members to nonzero values after the initialization function returns. However, for convenience, <b>SerCx2CustomReceiveCreate</b> uses the following default values if these members are zero:

If the calling driver sets <b>Exclusive</b> to <b>TRUE</b>, the <b>MinimumTransferUnit</b>, <b>Alignment</b>, and <b>MinimumTransactionLength</b> members must be zero. For more information, see <a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a>.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the custom-receive object, and to supply pointers to <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating custom-receive objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a>. For more information about custom-receive transactions, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a>
</dt>
<dt>
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a>
</dt>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a>
</dt>
<dt>
<a href="..\sercx\ns-sercx-_sercx2_custom_receive_config.md">SERCX2_CUSTOM_RECEIVE_CONFIG</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2_custom_receive_config_init.md">SERCX2_CUSTOM_RECEIVE_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveCreate method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

