---
UID: NF:sercx.SERCX2_PIO_TRANSMIT_CONFIG_INIT
title: SERCX2_PIO_TRANSMIT_CONFIG_INIT function
author: windows-driver-content
description: The SERCX2_PIO_TRANSMIT_CONFIG_INIT function initializes a SERCX2_PIO_TRANSMIT_CONFIG structure.
old-location: serports\sercx2_pio_transmit_config_init.htm
tech.root: serports
ms.assetid: B168C2EE-8D27-4A36-8B7F-C8EE719BFAC0
ms.date: 4/23/2018
ms.keywords: 2/SERCX2_PIO_TRANSMIT_CONFIG_INIT, SERCX2_PIO_TRANSMIT_CONFIG_INIT, SERCX2_PIO_TRANSMIT_CONFIG_INIT function [Serial Ports], serports.sercx2_pio_transmit_config_init
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
req.lib: 
req.dll: 
req.irql: Any level.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_PIO_TRANSMIT_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# SERCX2_PIO_TRANSMIT_CONFIG_INIT function


## -description


The <b>SERCX2_PIO_TRANSMIT_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a> structure.


## -parameters




### -param PioTransmitConfig [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a> structure that is to be initialized.


### -param EvtSerCx2PioTransmitWriteBuffer [in]

The value to load into the <b>EvtSerCx2PioTransmitWriteBuffer</b> member of the <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a>.


### -param EvtSerCx2PioTransmitEnableReadyNotification [in]

The value to load into the <b>EvtSerCx2PioTransmitEnableReadyNotification</b> member of the <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a>.


### -param EvtSerCx2PioTransmitCancelReadyNotification [in]

The value to load into the <b>EvtSerCx2PioTransmitCancelReadyNotification</b> member of the <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a>.


## -returns



None.




## -remarks



Your serial controller driver must use this function to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> method.

<b>SERCX2_PIO_TRANSMIT_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_PIO_TRANSMIT_CONFIG</b>), and sets three additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_PIO_TRANSMIT_CONFIG_INIT</b> call.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265334">SERCX2_PIO_TRANSMIT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a>
 

 

