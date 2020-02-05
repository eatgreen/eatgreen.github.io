auto plus10=[] (int i) {
                  return i+10;
               }

unnamed, inline function

[capture list] (para list) -> return type {function body}

  std::vector<int> v,w;

  for(int i=0; i<10; i++){
    v.push_back(i);
  }

  for(auto elem: v)
    std::cout<<elem<<std::endl;

  std::for_each(v.begin(), v.end(), [&](int& j){ return w.push_back(j); } );

  for(auto elem: v)
    std::cout<<elem<<std::endl;

