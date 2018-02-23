---
UID: NF:sercx.SERCX2_PIO_RECEIVE_CONFIG_INIT
title: SERCX2_PIO_RECEIVE_CONFIG_INIT function
author: windows-driver-content
description: The SERCX2_PIO_RECEIVE_CONFIG_INIT function initializes a SERCX2_PIO_RECEIVE_CONFIG structure.
old-location: serports\sercx2_pio_receive_config_init.htm
old-project: serports
ms.assetid: 08FBBC1D-EB2A-4178-9245-C3FF60424F95
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SERCX2_PIO_RECEIVE_CONFIG_INIT function [Serial Ports], 2/SERCX2_PIO_RECEIVE_CONFIG_INIT, serports.sercx2_pio_receive_config_init, SERCX2_PIO_RECEIVE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	2.0\Sercx.h
apiname:
-	SERCX2_PIO_RECEIVE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SERCX2_PIO_RECEIVE_CONFIG_INIT function


## -description


The <b>SERCX2_PIO_RECEIVE_CONFIG_INIT</b> function initializes a <a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a> structure.


## -syntax


````
VOID SERCX2_PIO_RECEIVE_CONFIG_INIT(
  _Out_ SERCX2_PIO_RECEIVE_CONFIG                        *PioReceiveConfig,
  _In_  PFN_SERCX2_PIO_RECEIVE_READ_BUFFER               EvtSerCx2PioReceiveReadBuffer,
  _In_  PFN_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION EvtSerCx2PioReceiveEnableReadyNotification,
  _In_  PFN_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION EvtSerCx2PioReceiveCancelReadyNotification
);
````


## -parameters




### -param PioReceiveConfig [out]

A pointer to the <a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a> structure that is to be initialized.


### -param EvtSerCx2PioReceiveReadBuffer [in]

The value to load into the <b>EvtSerCx2PioReceiveReadBuffer</b> member of the <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a>.


### -param EvtSerCx2PioReceiveEnableReadyNotification [in]

The value to load into the <b>EvtSerCx2PioReceiveEnableReadyNotification</b> member of the <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a>.


### -param EvtSerCx2PioReceiveCancelReadyNotification [in]

The value to load into the <b>EvtSerCx2PioReceiveCancelReadyNotification</b> member of the <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a>.


## -returns



None.




## -remarks



Your serial controller driver must use this function to initialize a <a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method.

<b>SERCX2_PIO_RECEIVE_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_PIO_RECEIVE_CONFIG</b>), and sets three additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_PIO_RECEIVE_CONFIG_INIT</b> call.




## -see-also

<a href="..\sercx\ns-sercx-_sercx2_pio_receive_config.md">SERCX2_PIO_RECEIVE_CONFIG</a>



<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_PIO_RECEIVE_CONFIG_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

