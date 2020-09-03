# -mergeSort

def merge(A, aux, left, right, mid):

    for p in range(left, right + 1):
        aux[p] = A[p]
    l = left
    r = right + 1
    for p in range(left, right + 1):
        if l > mid:
            A[p] = aux[r]
            r += 1
        elif r > right:
            A[p] = aux[l]
            l += 1
        elif aux[r] < aux[l]:
            A[p] = aux[r]
            r += 1
        else:
            A[p] = aux[l]
            l += 1

def mergeSort(A, aux, left, right):
    if right <= left:
        return

    mid = (left + right) // 2

    mergeSort(A, aux, left, mid)