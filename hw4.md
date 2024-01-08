# hw4
## 截圖
![IMG_0169](https://github.com/zhaohongg/yzu-swiftui-1101453/assets/149959884/dff5d8ec-df63-4636-99d6-6c2a86bbfa9e)
![IMG_0168](https://github.com/zhaohongg/yzu-swiftui-1101453/assets/149959884/03aae38b-0aed-4d8d-b9d4-49556bf34187)
![IMG_0167](https://github.com/zhaohongg/yzu-swiftui-1101453/assets/149959884/258b6047-ad0e-418c-ba2b-bcfe418c2819)


## 程式碼
```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack{
            Text ("寶可夢圖鑑")
                .font (.largeTitle)
                . fontWeight(.heavy)
                .foregroundStyle(.primary)
            TabView{
                WelcomeView()
                    .tabItem {
                        Image (systemName: "list.dash")
                        Text ("主頁")
                    }
                PokView()
                    .tabItem {
                        Image (systemName: "list.dash")
                        Text ("妙蛙")
                    }
                PokView2()
                    .tabItem {
                        Image (systemName: "list.dash")
                        Text ("烏龜")
                    }
            }
        }
    }
 }

struct WelcomeView: View{
    var body: some View{
        VStack{
            Image("圖鑑")
                .resizable()
                .aspectRatio(contentMode: .fit)
            Text("圖鑑")
                .fontWeight(.heavy)
                .lineSpacing(20)
                .font(.system(size: 32.0))
                .foregroundColor(.black)
                .frame(width: 350, height: 150, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
                .cornerRadius(20.0)
                .multilineTextAlignment(.center)
        }
    }
}

struct pok:Identifiable{
    var id = UUID()
    var name:String
}

var poks = [
    pok(name: "妙蛙種子"),
    pok(name: "妙蛙草"),
    pok(name: "妙蛙花"),
    pok(name: "超級妙蛙花"),
    pok(name: "妙蛙花超極巨化")
]
var poks2 = [
    pok(name: "傑尼龜"),
    pok(name: "卡咪龜"),
    pok(name: "水箭龜"),
    pok(name: "超級水箭龜"),
    pok(name: "水箭龜超極巨化")
]

struct BasicImageRow: View{
    var thispok:pok
    var body: some View{
        HStack{
            Image(thispok.name)
                .resizable()
                .frame(width: 40, height: 40)
                .cornerRadius(5)
            Text(thispok.name)
        }
    }
}

struct BasicImageRow2: View{
    var thispok:pok
    var body: some View{
        HStack{
            Image(thispok.name)
                .resizable()
                .frame(width: 40, height: 40)
                .cornerRadius(5)
            Text(thispok.name)
        
        }
    }
}

struct PokView: View{
    var body: some View{
        NavigationStack{
            List(poks){ pokItem in BasicImageRow(thispok: pokItem) 
                    
            }
            .navigationTitle("妙蛙家族")
        }
        
    }
}

struct PokView2: View{
    var body: some View{
        NavigationStack{
            List(poks2){pokItem in BasicImageRow2(thispok: pokItem)}
                .navigationTitle("烏龜家族")
        }
    }
}
```
