inline void bfs(vector<int> &d, int x){
	d[x] = 0;
	queue<pair<int,int> >q;
	q.push({x,d[x]});
	while(!q.empty()){
		auto it = q.front();
		q.pop();
		for(auto i : g[it.F]){
			if(d[i] > it.S + 1){
				d[i] = it.S + 1;
				q.push({i,d[i]});
			}
		}
	}
}
