class Planet:
    def __init__(self,pname,agas,moons,rings):
        self.pname = pname
        self.agas = agas
        self.moons = moons
        self.rings = rings
class Calculation:
    def __init__(self,plist):
        self.plist = plist
    
    def moon(self):
        count=0
        for i in self.plist:
            if(i.rings=='Yes'):
                count+=i.moons
        print(count)
    def gas(self):
        dic = {}
        for i in self.plist:
            for j in i.agas:
                if j in dic:
                    dic[j]+=1
                else:
                    dic[j]=1
        a = sorted(dic.items(), key=lambda x: x[1], reverse=True)
        print(a[0][0])
t = int(input())
plist = []
for i in range(t):
    pname = input()
    agas = [item for item in input().split(",")]
    moons = int(input())
    rings = input()
    plist.append(Planet(pname,agas,moons,rings))
cobj = Calculation(plist)
cobj.moon()
cobj.gas()

