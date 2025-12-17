# Quick-sort
def quick_sort(arr, low, high):
    if low < high:
        p = partition(arr, low, high)   # menentukan pivot
        quick_sort(arr, low, p - 1)     # kiri pivot
        quick_sort(arr, p + 1, high)    # kanan pivot

def partition(arr, low, high):
    pivot = arr[high]   # pivot memakai elemen terakhir (Lomuto)
    i = low - 1

    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]

    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1

# Program utama
data = [30, 12, 50, 22, 7, 18]
print("Data sebelum diurutkan:", data)

quick_sort(data, 0, len(data) - 1)

print("Data setelah Quick Sort:", data).
