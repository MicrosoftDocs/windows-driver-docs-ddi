---
UID: NF:sercx.SerCx2SystemDmaTransmitGetDmaEnabler
title: SerCx2SystemDmaTransmitGetDmaEnabler function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitGetDmaEnabler method gets the DMA enabler for the system DMA controller that is used for system-DMA-transmit transactions.
old-location: serports\sercx2systemdmatransmitgetdmaenabler.htm
tech.root: serports
ms.assetid: 5B6893D4-51ED-483C-87F4-0404C48E100F
ms.date: 4/23/2018
ms.keywords: 2/SerCx2SystemDmaTransmitGetDmaEnabler, SerCx2SystemDmaTransmitGetDmaEnabler, SerCx2SystemDmaTransmitGetDmaEnabler method [Serial Ports], serports.sercx2systemdmatransmitgetdmaenabler
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
-	SerCx2SystemDmaTransmitGetDmaEnabler
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2SystemDmaTransmitGetDmaEnabler function


## -description


The <b>SerCx2SystemDmaTransmitGetDmaEnabler</b> method gets the DMA enabler for the system DMA controller that is used for system-DMA-transmit transactions.


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## -returns



This method returns a WDFDMAENABLER handle to the framework DMA enabler object that represents the system DMA controller that is used for system-DMA-transmit transactions.




## -remarks



If necessary, your serial controller driver can call this method to configure special features in the system DMA controller. The driver can use the DMA enabler returned by this method to specify DMA settings that were not supplied in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265344">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure that the driver previously passed as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a> method. Or, the driver can use the DMA enabler to change the DMA settings that were previously specified in this structure.

For more information about DMA enabler objects, see <a href="https://msdn.microsoft.com/87735776-c371-425b-bc53-0c68375c9562">Enabling DMA Transactions</a>. For more information about system-DMA-transmit transactions, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265344">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a>
 

 

