---
UID: NF:gpioclx.GPIO_CLX_AcquireInterruptLock
title: GPIO_CLX_AcquireInterruptLock function
author: windows-driver-content
description: The GPIO_CLX_AcquireInterruptLock method acquires an interrupt lock on a bank of pins in the general-purpose I/O (GPIO) controller.
old-location: gpio\gpio_clx_acquireinterruptlock.htm
old-project: GPIO
ms.assetid: E0332415-1028-489B-AA81-DF8AEE0A28E8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO_CLX_AcquireInterruptLock method [Parallel Ports], GPIO.gpio_clx_acquireinterruptlock, GPIO_CLX_AcquireInterruptLock, gpioclx/GPIO_CLX_AcquireInterruptLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: gpioclx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Msgpioclxstub.lib
req.dll: 
req.irql: DIRQL or at PASSIVE_LEVEL. See Remarks.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Msgpioclxstub.lib
-	Msgpioclxstub.dll
apiname:
-	GPIO_CLX_AcquireInterruptLock
product: Windows
targetos: Windows
req.typenames: GPIO_CONNECT_IO_PINS_MODE, *PGPIO_CONNECT_IO_PINS_MODE
---

# GPIO_CLX_AcquireInterruptLock function


## -description


The <b>GPIO_CLX_AcquireInterruptLock</b> method acquires an interrupt lock on a bank of pins in the general-purpose I/O (GPIO) controller.


## -syntax


````
VOID GPIO_CLX_AcquireInterruptLock(
  _In_ PVOID   Context,
  _In_ BANK_ID BankId
);
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>. The GPIO framework extension (GpioClx) passes this pointer value as a parameter to the callback functions that are implemented by the GPIO controller driver.


### -param BankId [in]

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1.


## -returns



None.




## -remarks



A GPIO controller driver thread calls this method to synchronize to the interrupt service routine (ISR) in GpioClx. While the caller holds the interrupt lock, the ISR cannot call driver-implemented callback functions to access GPIO registers in the specified bank. A GPIO controller driver should call this method before it tries to access GPIO registers that might be accessed by the GpioClx ISR.

The GpioClx ISR calls driver-implemented callback functions to access interrupt status and enable registers in the GPIO controller. Depending on the capabilities of the GPIO controller, the ISR is called either at DIRQL or at PASSIVE_LEVEL. For more information, see <a href="https://msdn.microsoft.com/638B52A0-CB8D-4A79-B7D1-ED2474E46DAE">Interrupt-Related Callbacks</a>.

If the GpioClx ISR accesses these interrupt registers at DIRQL, <b>GPIO_CLX_AcquireInterruptLock</b> raises the calling thread's IRQL to the DIRQL at which the ISR runs. If the ISR runs at PASSIVE_LEVEL, this method does not change the calling thread's IRQL.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439494">GPIO_CLX_ReleaseInterruptLock</a> method releases an interrupt lock that was acquired in a previous call to <b>GPIO_CLX_AcquireInterruptLock</b>. The <b>BankId</b> parameter specifies the bank that is affected by the lock. To release a lock on a bank, the <b>BankId</b> parameter of the <b>GPIO_CLX_ReleaseInterruptLock</b> call must match the <b>BankId</b> parameter of the <b>GPIO_CLX_AcquireInterruptLock</b> call that acquired the lock. If the <b>GPIO_CLX_AcquireInterruptLock</b> call raised the calling thread's IRQL, <b>GPIO_CLX_ReleaseInterruptLock</b> restores this thread's original IRQL.

The GPIO controller driver can independently acquire and release interrupt locks on the various banks in the GPIO controller. However, it is a fatal error for the driver to try to acquire a lock on a particular bank if the driver already holds a lock on this bank.

If the <i>Context</i> parameter is NULL or points to an invalid GPIO device context, this method causes a bug check in debug builds of GpioClx.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439494">GPIO_CLX_ReleaseInterruptLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_AcquireInterruptLock method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

