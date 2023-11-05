# 作業3
![作業3](https://github.com/zhaohongg/yzu-swiftui-1101453/assets/149959884/050e5b5a-5af9-474c-9a86-0fa42dce88e8)

## c
```swift

import SwiftUI

struct ContentView: View {
    var body: some View {
        ZStack{
            Rectangle()
                .fill(Color.white)
                .frame(minWidth: 0, idealWidth: 100, maxWidth: .infinity, minHeight: 0, idealHeight: 100, maxHeight: .infinity)
                .ignoresSafeArea(.all)
            Shelfview()
            VStack{
                FirstRowView()
                    .offset(x:0, y:-80)
                SecondRowView()
                    .offset(x:0, y:30)
                ThirdRowView()
                    .offset(x:0, y:80)
            }
            
        }
    }
}

struct Shelfview: View{
    var body: some View{
        VStack{
            Spacer(minLength: 150)
            Image("木板")
                .resizable()
                .frame(height: 300, alignment: .center)
                .offset(y: 80)
            Image("木板")
                .resizable()
                .frame(height: 200, alignment: .center)
            Image("木板")
                .resizable()
                .frame(height: 200, alignment: .center)
        }
    }
}

struct FirstRowView: View{
    var body: some View{
        VStack{
            HStack{
                Image("綠茶")
                    .resizable()
                    .frame(height: 180, alignment: .center)

                    .offset(x:0, y:30)
                Image("藍筆")
                    .resizable()
                    .frame(height: 100, alignment: .center)
                    .offset(x:0, y:70)
                Image("立可帶")
                    .resizable()
                    .frame(height: 80, alignment: .center)
                    .offset(x:0, y:80)
            }
            
        }
    }
}    

struct SecondRowView: View{
    var body: some View{
        HStack{
            Image("一元")
                .resizable()
                .frame(height: 120, alignment: .center)
            Image("五元")
                .resizable()
                .frame(height: 120, alignment: .center)
                .offset(x:0, y:3)
            Image("協天宮")
                .resizable()
                .frame(height: 120, alignment: .center)
        }
    }
}

struct ThirdRowView: View{
    var body: some View{
        HStack{
            Image("湯匙")
                .resizable()
                .frame(height: 160, alignment: .center)
            Image("瓶蓋")
                .resizable()
                .frame(height: 160, alignment: .center)
            Image("指甲剪")
                .resizable()
                .frame(height: 160, alignment: .center)
        }
    }
}


```
