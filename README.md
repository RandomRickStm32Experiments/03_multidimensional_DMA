# multidimensional_DMA
Follow on from [02_stm32f0_ADC_DMA_multichannel](https://github.com/RandomRickStm32Experiments/02_stm32f0_ADC_DMA_multichannel).

That code works, but I don't like the overhead of all the DMA interrupts
happening all the time.  Better to sample a bunch of times and then just process at the end, producing many fewer DMA ints.

Now,in this project we will  sample not just 3 DMA channels, but repeatedly, creating a 2D array

## Goal 1 [done]
sample 3 channels into a DMA - that's done already in stm32f0_ADC_DMA_multichannel_continuous_sampling project.
Expand then expand that to store a succession of these 3-sample sets into an array, like this:

CH1[0]  
CH2[0]  
CH3[0]

CH1[1]  
CH2[1]  
CH3[1]  

## Goal 2 [not started]
don't run the ADC all the time - trigger either with `HAL_ADC_START_DMA` in Tim1 callback or by a Tim1 event.
