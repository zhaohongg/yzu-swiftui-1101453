# 作業1

![作業1](https://github.com/zhaohongg/yzu-swiftui-1101453/assets/149959884/f07e4d29-7bb2-473d-8158-b1ce6c37c290)

## c
```swift

import SwiftUI

struct ContentView: View {
    var body: some View {
        ZStack{
            Rectangle()
                .fill(Color(red: 100/255, green: 205/255, blue: 203/255))
                .frame(minWidth: 0, idealWidth: 100, maxWidth: .infinity, minHeight: 0, idealHeight: 100, maxHeight: .infinity, alignment: .center)
                .ignoresSafeArea(.all)
            VStack{
                Text("1101453     陳昭宏")
                    .font(.system(size: 35, weight: .bold))
                    .frame(width: 400, height: 20, alignment: .center)
                    .offset(x: 0, y: 100)
                
                Text("我是阿志 !")
                    .fontWeight(.heavy)
                    .lineSpacing(10)
                    .font(.system(size: 22))
                    .foregroundColor(.white)
                    .frame(width: 400, height: 200, alignment: .top)
                    .padding(.top, 20)
                
                    .cornerRadius(60)
                    .offset(x: 0, y:90)
                    .multilineTextAlignment(.center)
                
                Image("Me")
                    .resizable()
                    .aspectRatio(contentMode: .fill)
                    .frame(width: 400, height: 500, alignment: .trailing)
                    
    
            }
            Image(systemName: "graduationcap.fill")
                .foregroundColor(.blue)
                .font(.system(size: 120))
                .position(x: 180, y: 400)
        }
    }
}


```
