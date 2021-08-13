import statistics
import sys

def arithmeticSquare(G): #returns int
    return findNonMidProgressions(G) + findMidProgressions(G)

def findMidProgressions(G):
    n = len(G)
    hori = G[1]
    vert = [G[i][1] for i in range(n)]
    dDiag = [G[i][i] for i in range(n)]
    uDiag = [G[i][n-i-1] for i in range(n)]
    middles = list(map(findMiddleElement, [hori,vert,dDiag,uDiag]))
    try:
        mode = statistics.mode(middles)
        if mode == None: maxCount = 0
        else: maxCount = middles.count(statistics.mode(middles))
    except:
        maxCount = 1
    return maxCount

def findMiddleElement(seq): #returns int or None
    zeroth,first,second = seq
    diff = second - zeroth
    if diff % 2 == 1: return None
    return zeroth + diff//2

def findNonMidProgressions(G): #returns int
    n = len(G)
    top = G[0]
    bottom = G[n-1]
    
    left = [G[i][0] for i in range(n)]
    right = [G[i][n-1] for i in range(n)]
    
    return sum(list(map(isArithProgression, [top,bottom,left,right])))

def isArithProgression(seq): #returns bool converted to int
    zeroth,first,second = seq
    return int(second - first == first - zeroth)
    
def printArray(A):
    for item in A: print(item)

def main(data):
    N = int(data[0])
    n = 3
    for i in range(N):
        tmp = data[n*i+1:n*(i+1)+1]
        G = [list(map(lambda x: int(x), line.split())) for line in tmp]
        middle = [G[1][0], 0, G[1][1]]
        G[1] = middle
        #print("G: ", end="")
        #printArray(G)
        print("Case #", end = '')
        print(i+1, end = '')
        print(":", arithmeticSquare(G))

if __name__ == "__main__":
    #data = [line.rstrip() for line in sys.stdin.readlines()]
    #data = "3\n3 4 11\n10 9\n-1 6 7\n4 1 6\n3 5\n2 5 6\n9 9 9\n9 9\n9 9 9"
    #main(data.splitlines())
    main(data)
