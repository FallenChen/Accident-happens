
# A

best case: blocks are mapped sequential and on same cylinder. just seek data once.

T_avg_seek = 4ms
T_avg_rotation = 2ms

file size 2MB, block size 512B, block count 2MB/512B = 4000

Block Per Track = 1000, so we need rotate 4 loop to read all data

T_transfer = T_rotation = T_max_rotation * 4 = 16ms

T_access = 22ms


# B

T_access = 4000 * (T_avg_seek + T_avg_rotation) = 24s
