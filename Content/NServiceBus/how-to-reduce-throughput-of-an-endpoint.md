---
title: How to Reduce Throughput of an Endpoint?
summary: 'Two ways to decrease throughput of an endpoint: TransportConfig in endpoint config or program the API.'
tags: []
---

There are two ways to decrease receiving throughput of an endpoint.

Edit the `TransportConfig` section in the endpoint config file:


```XML
<TransportConfig MaximumConcurrencyLevel="5" MaxRetries="2" MaximumMessageThroughputPerSecond="10"/>
```

In V4 you can also use the API:​

<!-- import ChangeThroughputV4 -->

```C#
public class ChangeThroughtput : IWantToRunWhenConfigurationIsComplete
{
    public UnicastBus Bus { get; set; }

    public void Run()
    {
            Bus.Transport.ChangeMaximumThroughputPerSecond(10);
    }
}
```




