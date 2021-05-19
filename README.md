# combinationsum_2

class Solution:
def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
ans=[]
temp=[]
index=0
if sum(candidates)<target:
return None
else:
self.com(ans,temp,candidates,target,index)
return ans
def com(self,ans,temp,a,target,index):
if target==0:
Ans=sorted(temp)
if Ans not in ans:
ans.append(Ans)
return

    for i in range(index,len(a)):
        if (target-a[i])>=0:
            temp.append(a[i])
            self.com(ans,temp,a,target-a[i],i+1)
            temp.remove(a[i])
