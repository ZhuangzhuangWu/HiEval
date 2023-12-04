

A mapping describes how the computation and tensors in a workload are partitioned and scheduled across the hardware substrate. A mapping specification for HiEval is effectively a JSON-based representation of an annotated loop nest. 

# An example of mapping describes
```
{
    "conv5":{
        "type": "Conv", 
        "N": 4, "K": 256, "C": 192, "R": 3, "S": 3, "Y": 13, "X": 13, "Stride": 1, "Padding": 0,
        "L3_N": 4, "L3_K": 64, "L3_C": 2, "L3_R": 3, "L3_X": 13, "L3_Y": 13, "L3_S": 3,
        "L2_N": 4, "L2_K": 2, "L2_C": 2, "L2_R": 3, "L2_X": 13, "L2_Y": 13, "L2_S": 3,
        "L1_N": 4, "L1_K": 1, "L1_C": 1, "L1_R": 3, "L1_X": 13, "L1_Y": 1, "L1_S": 1,
        "order_L3": ["y", "x", "n", "c", "k", "r", "s"],
        "order_L2": ["x", "n", "c", "k", "y", "r", "s"],
        "order_L1": ["x", "n", "c", "k", "y", "r", "s"],
        "space_x": ["y"], "space_y": ["s","k","c"],
    }
}
```

Type of Operation: The operation is a convolution (Conv).

Dimensions: The dimensions of the convolution are specified, including the batch size (N), number of filters (K), input channels (C), filter height (R) and width (S), input height (Y) and width (X), stride (Stride), and padding (Padding).

Hierarchy Levels: The convolution operation is mapped across different hardware hierarchy levels (L1, L2, L3), each with its own set of dimensions.

Order of Iteration: The order in which the nested loops are traversed is specified for each hierarchy level (L1, L2, L3). This helps in understanding the loop nest structure.

Spatial Order: Specifies the spatial order for each dimension in the convolution (x and y). This provides insights into the spatial arrangement of computations.

Cluster: Indicates the clustering of computations. In this case, computations are clustered based on the filter (k).
