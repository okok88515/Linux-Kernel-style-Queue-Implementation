# Linux-Kernel-style-Queue-Implementation
本專案實作了一個 Linux Kernel 風格的 Queue（雙向鏈結串列），支援多種操作，例如插入、刪除、反轉、排序與合併等，並搭配 list_head 巨集實現高效且靈活的鏈結操作。

📂 檔案結構

queue.h：定義 element_t、queue_context_t 結構與函式介面。

queue.c：主要的 queue 函式實作。

list.h：Linux kernel 的 linked list 宏（如果有包含）。

✨ 功能說明
基本操作

q_new()：建立一個新的空 queue。

q_free()：釋放 queue 及所有元素。

q_insert_head()：從 queue 開頭插入字串。

q_insert_tail()：從 queue 尾端插入字串。

q_remove_head()：移除並回傳 queue 開頭元素。

q_remove_tail()：移除並回傳 queue 尾端元素。

q_size()：回傳 queue 的大小。

特殊刪除

q_delete_mid()：刪除中間節點。

q_delete_dup()：刪除重複字串的節點（假設 queue 已排序）。

節點操作

q_swap()：交換相鄰兩個節點。

q_reverse()：反轉整個 queue。

q_reverseK()：每 k 個節點一組進行反轉。

排序與合併

q_sort()：將 queue 排序（升冪或降冪）。

q_merge()：將多個 queue 合併為一個排序好的 queue。

q_ascend()：刪除右側存在較小值的節點。

q_descend()：刪除右側存在較大值的節點。

📌 特點

採用 Linux Kernel Doubly Linked List (list_head) 巨集進行管理。

多數功能對應到 LeetCode 經典題目，例如：

Delete the Middle Node of a Linked List

Remove Duplicates from Sorted List II

Swap Nodes in Pairs

Reverse Nodes in k-Group

Sort List

Merge k Sorted Lists

🚀 編譯與執行
# 編譯
gcc -o queue main.c queue.c -Wall -Wextra -g

# 執行
./queue


（需搭配 main.c 測試程式）
