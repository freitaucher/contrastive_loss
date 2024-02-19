## What it is all about

Typical problem while applying the autencoders (AE) is that we are looking not for
*all* possible outliers delivered by the AE, but only for the *specific ones*, let's call them "defects". E.g., by applying an AE to a production line which produces defects rarely, it might offen happen, that the most types of outliers are estimated by an AE much stronger than the real defects.


If you do not use  some specific metrics, your AE will not be able to distinguish them from the rest of outliers. In this case, it appears very helpful to use some prior knowledge about this specific type of outliers, if available. The basic idea is to tell the AE, what type of elements he should not learn. In the context of the model fitting it can be realized by introducing some extra loss penalty for those elements: `loss = -(x-x')**2`, where `x` is the input and `x'=model(x)` is the output of the AE model. Minus sign takes care of the fact that the difference `(x-x')**2` must be maximized if the element represents a "defect".


